# EdgeScript scenarios

This topic describes the application scenarios of EdgeScript, including authentication logic customization, request header and response header customization, rewrite and redirect customization, M3U8 rewrite customization, cache control customization, and throttling customization.

## Customize the authentication logic

The following example shows custom authentication algorithms:

-   Requirements
    -   Request URL format: `/path/digest/?.ts? key=&t=`
    -   For `.ts` requests, the requirements for customizing hotlinking protection are:
        -   Rule 1: If the request does not contain the `t` or `key` parameter, the CDN node returns the 403 status code and adds the `X-AUTH-MSG` response header to indicate the failure cause.
        -   Rule 2: The `t` parameter specifies the expiration time. If the specified `t` parameter is earlier than the current time, the CDN node returns the 403 status code and adds the `X-AUTH-MSG` response header to indicate the failure cause.
        -   Rule 3: The CDN node compares the `md5` parameter with the `digest` parameter. If `md5` does not match `digest`, the CDN node returns the 403 status code.

            Value format of the md5 parameter: `Private key + Path + File name.extension`.

-   Corresponding EdgeScript script:

    ```
    if eq(substr($uri, -3, -1), '.ts') {
    
       if or(not($arg_t), not($arg_key)) {
           add_rsp_header('X-AUTH-MSG', 'auth failed - missing necessary arg')
           exit(403)
       }
    
       t = tonumber($arg_t)
       if not(t) {
           add_rsp_header('X-AUTH-MSG', 'auth failed - invalid time')
           exit(403)
       }
    
       if gt(now(), t) {
           add_rsp_header('X-AUTH-MSG', 'auth failed - expired url')
           exit(403)
       }
    
        pcs = capture_re($request_uri,'^/([^/]+)/([^/]+)/([^?] +)\?(.*)')
        sec1 = get(pcs, 1)
        sec2 = get(pcs, 2)
        sec3 = get(pcs, 3)
    
        if or(not(sec1), not(sec2), not(sec3)) {
            add_rsp_header('X-AUTH-MSG', 'auth failed - malformed url')
            exit(403)
        }
    
        key = 'b98d643a-9170-4937-8524-6c33514bbc23'
        signstr = concat(key, sec1, sec3)
        digest = md5(signstr)
        if ne(digest, sec2) {
            add_rsp_header('X-AUTH-DEBUG', concat('signstr: ', signstr))
            add_rsp_header('X-AUTH-MSG', 'auth failed - invalid digest')
            exit(403)
        }
    
    }
    ```


## Customize request headers and response headers

The following example shows automatic file renaming:

-   Requirements

    If the `filename` parameter is set, the file is automatically renamed the value specified by the `filename` parameter. If no file name is specified, the default file name is used.

-   Corresponding EdgeScript script:

    ```
    // The value for the filename parameter is enclosed in a pair of double quotation marks (""). The string "34" is the ASCII string for double quotation marks. It can be converted back to the quotation mark string ("") through the tochar function.
    // Example: add_rsp_header('Content-Disposition', concat('attachment;filename=', tochar(34), filename, tochar(34)))
    // Output: Content-Disposition: attachment;filename="monitor.apk"
    
    if $arg_filename {
        hn = 'Content-Disposition'
        hv = concat('attachment;filename=', $arg_filename)
        add_rsp_header(hn, hv)
    }
    ```


## Customize rewrites or redirects

The following examples show how to customize rewrites and redirects:

-   Rewrite a URI.
    -   Requirements

        Configure Alibaba Cloud Content Delivery Network \(CDN\) to rewrite `/hello` as `/index.html`. As a result, the URI of the back-to-origin request is changed to `/index.html` and the parameters remain unchanged.

    -   Corresponding EdgeScript script:

        ```
        if match_re($uri, '^/hello$') {
            rewrite('/index.html', 'break')
        }
        ```

-   Rewrite a file extension.
    -   Requirements

        Configure Alibaba Cloud CDN to rewrite `/1.txt` as `/1<url parameter type\>`. For example, `/1.txt? type=mp4` will be rewritten as `/1.mp4? type=mp4` in back-to-origin requests and cached on CDN nodes.

    -   Corresponding EdgeScript script:

        ```
        if and(match_re($uri, '^/1.txt$'), $arg_type) {
             rewrite(concat('/1.', $arg_type), 'break')
        }
        ```

-   Convert a file extension to lowercase letters.
    -   Requirements

        Convert the URI string to lowercase letters.

    -   Corresponding EdgeScript script:

        ```
        pcs = capture_re($uri, '^(. +%.)([ ^.]+)')
        section = get(pcs, 1)
        postfix = get(pcs, 2)
        
        if and(section, postfix) {
            rewrite(concat(section, lower(postfix)), 'break')
        }
        ```

-   Add a URI prefix.
    -   Requirements

        Configure Alibaba Cloud CDN to rewrite `^/nn_live/(. *)` as `/3rd/nn_live/$1`.

    -   Corresponding EdgeScript script:

        ```
        pcs = capture_re($uri, '^/nn_live/(.*)')
        sec = get(pcs, 1)
        
        if sec {
             dst = concat('/3rd/nn_live/', sec)
             rewrite(dst, 'break')
        }
        ```

-   Set a 302 redirect.
    -   Requirements

        Perform a 302 redirect to `/app/movie/pages/index/index.html` for the `/` root directory.

    -   Corresponding EdgeScript script:

        ```
        if eq($uri, '/') {
            rewrite('/app/movie/pages/index/index.html', 'redirect')
        }
        ```

-   Set a 302 redirect to HTTPS URIs
    -   Requirements

        Redirect the following URIs that match the `^/$` root directory to `https://rtmp.cdnpe.com/index.html`. You can specify the destination URI as needed.

        -   `http://rtmp.cdnpe.com`
        -   `https://rtmp.cdnpe.com`
    -   Corresponding EdgeScript script:

        ```
        if eq($uri, '/') {
            rewrite('https://rtmp.cdnpe.com/index.html', 'redirect')
        }
        ```


## Customize cache control

The following example shows how to customize the cache duration:

-   Requirements

    Customize the resource cache duration based on various conditions.

-   Corresponding EdgeScript script:

    ```
    // Note: Set the cache duration for status codes responded to requests whose URIs start with "/image". Set 10 seconds for the 301 status code and 5 seconds for the 302 status code.
    if match_re($uri, '^/image') {
        set_cache_ttl('code', '301=10,302=5')
    }
    
    if eq(substr($uri, -4, -1), '.mp4') {
        set_cache_ttl('path', 5)
    }
    if match_re($uri, '^/201801/mp4/') {
        set_cache_ttl('path', 50)
    }
    if match_re($uri, '^/201802/flv/') {
        set_cache_ttl('path', 10)
    }
    ```


## Customize throttling policies

The following example shows how to customize a throttling policy:

-   Requirements

    If the `sp` and `unit` parameters are set, throttling is implemented. The `sp` parameter specifies the throttling threshold. The `unit` parameter specifies the unit. The unit can be KB or MB.

-   Corresponding EdgeScript script:

    ```
    if and($arg_sp, $arg_unit) {
        sp = tonumber($arg_sp)
        if not(sp) {
            add_rsp_header('X-LIMIT-DEBUG', 'invalid sp')
            return false
        }
    
        if and(ne($arg_unit, 'k'), ne($arg_unit, 'm')) {
            add_rsp_header('X-LIMIT-DEBUG', 'invalid unit')
            return false
        }
    
        add_rsp_header('X-LIMIT-DEBUG', concat('set on: ', sp, $arg_unit))
        limit_rate(sp, $arg_unit)
        return true
    }
    ```


