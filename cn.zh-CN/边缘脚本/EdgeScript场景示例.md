# EdgeScript场景示例

本文为您介绍EdgeScript的定制化鉴权逻辑、定制化请求头和响应头控制、定制化改写和重定向、定制化M3U8改写、定制化缓存控制、定制化限速的场景示例。

## 定制化鉴权逻辑

自定义鉴权算法场景示例如下：

-   需求
    -   请求URL格式：`/path/digest/?.ts?key=&t=`。
    -   针对`.ts`类请求，自定义防盗链需求如下：
        -   规则1：参数`t`或参数`key`不存在，响应403，增加响应头`X-AUTH-MSG`标识鉴权失败原因。
        -   规则2：参数`t`表示过期时间，若参数`t`小于当前时间，则响应403，增加响应头`X-AUTH-MSG`标识鉴权失败原因。
        -   规则3：`md5`与`digest`匹配。若`md5`与`digest`不匹配，响应403。

            md5取值格式为：`私钥 + path + 文件名.后缀`。

-   对应的EdgeScript规则

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
    
        pcs = capture_re($request_uri,'^/([^/]+)/([^/]+)/([^?]+)\?(.*)')
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


## 定制化请求头和响应头控制

文件自动重命名场景示例如下：

-   需求

    有参数`filename`时，自动重命名为`filename`；无参数时，使用默认命名。

-   对应的EdgeScript规则

    ```
    //filename增加双引号，34为双引号的ascii，可经tochar转回字符串。
    //示例：add_rsp_header('Content-Disposition', concat('attachment;filename=', tochar(34), filename, tochar(34)))
    //输出：Content-Disposition: attachment;filename="monitor.apk"
    
    if $arg_filename {
        hn = 'Content-Disposition'
        hv = concat('attachment;filename=', $arg_filename)
        add_rsp_header(hn, hv)
    }
    ```


## 定制化改写和重定向

定制化改写和重定向场景示例如下：

-   精确URI改写
    -   需求

        将用户请求`/hello`在CDN内部改写成`/index.html`，回源和缓存的URI都将变成`/index.html`，参数保持原样。

    -   对应的EdgeScript规则

        ```
        if match_re($uri, '^/hello$') {
            rewrite('/index.html', 'break')
        }
        ```

-   文件后缀改写
    -   需求

        将用户请求`/1.txt`，通过302重定向到`/1.<url参数type\>`，例如：`/1.txt?type=mp4`将会被改成`/1.mp4?type=mp4`回源并缓存。

    -   对应的EdgeScript规则

        ```
        if and(match_re($uri, '^/1.txt$'), $arg_type) {
             rewrite(concat('/1.', $arg_type), 'break')
        }
        ```

-   文件后缀小写化
    -   需求

        将URI改成小写。

    -   对应的EdgeScript规则

        ```
        pcs = capture_re($uri, '^(.+%.)([^.]+)')
        section = get(pcs, 1)
        postfix = get(pcs, 2)
        
        if and(section, postfix) {
            rewrite(concat(section, lower(postfix)), 'break')
        }
        ```

-   添加URI前缀
    -   需求

        将用户请求`^/nn_live/(.*)`，通过302重定向到`/3rd/nn_live/$1`。

    -   对应的EdgeScript规则

        ```
        pcs = capture_re($uri, '^/nn_live/(.*)')
        sec = get(pcs, 1)
        
        if sec {
             dst = concat('/3rd/nn_live/', sec)
             rewrite(dst, 'break')
        }
        ```

-   302重定向
    -   需求

        将根目录`/`，302重定向到`/app/movie/pages/index/index.html`页面。

    -   对应的EdgeScript规则

        ```
        if eq($uri, '/') {
            rewrite('/app/movie/pages/index/index.html', 'redirect')
        }
        ```

-   302重定向HTTPS
    -   需求

        将如下URI（对根目录匹配，`^/$`）跳转到`https://rtmp.cdnpe.com/index.html` ，跳转后的URI可按需填写。

        -   `http://rtmp.cdnpe.com`
        -   `https://rtmp.cdnpe.com`
    -   对应的EdgeScript规则

        ```
        if eq($uri, '/') {
            rewrite('https://rtmp.cdnpe.com/index.html', 'redirect')
        }
        ```


## 定制化缓存控制

自定义缓存时长的场景样例如下：

-   需求

    根据各类条件，自定义资源缓存时长。

-   对应的EdgeScript规则

    ```
    //说明：/image开头的uri，针对响应码设置缓存时长，301缓存10s，302缓存5s
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


## 定制化限速

自定义限速值的场景样例如下：

-   需求

    如果有参数`sp`和`unit`，则实施限速。`sp`参数指明限速数值，`unit`为参数单位，KB或MB。

-   对应的EdgeScript规则

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


