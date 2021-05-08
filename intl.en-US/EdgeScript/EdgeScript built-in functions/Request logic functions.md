# Request logic functions

This topic describes the syntax, description, parameters, and return values of request logic functions. This topic also provides examples of these functions.

## server\_addr

Queries the IP addresses of servers that receive the current request. The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|server\_addr\(\)|
|Parameter|N/A|
|Example|```
s_addr = server_addr()
say(concat('s_addr:', s_addr))
``` |
|Return value|Returns the IP addresses of the servers in a string.|

## server\_port

Queries the server port that receives the current request. The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|server\_port\(\)|
|Parameter|N/A|
|Example|```
s_addr = server_addr()
say(concat('s_addr:', s_addr))
``` |
|Return value|Returns the server port that receives the current request. Data type: numeric.|

## client\_addr

Queries the IP address of a client. The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|client\_addr\(\)|
|Parameter|N/A|
|Example|```
c_addr = client_addr()
c_port = client_port()
say(concat('c_addr:', c_addr))
say(concat('c_port:', tostring(c_port)))
``` |
|Return value|Returns the IP address of the specified client in a string.|

## client\_country

Queries the country code of a client. The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|client\_country\(\)|
|Parameter|N/A|
|Example|```
c_country = client_country()
c_region = client_region()
c_isp = client_isp()
if c_country {
    say(concat('client_country:', c_country))
}
if c_region {
    say(concat('client_region:', c_region))
}
if c_isp {
    say(concat('client_isp:', c_isp))
}
``` |
|Return value|Returns the country code of the specified client in a string. For more information about country codes, see [Country codes](/intl.en-US/EdgeScript/EdgeScript built-in functions/Appendix.md).|

## client\_region

Queries the administrative division code of a client. The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|client\_region\(\)|
|Parameter|N/A|
|Example|```
c_country = client_country()
c_region = client_region()
c_isp = client_isp()
if c_country {
    say(concat('client_country:', c_country))
}
if c_region {
    say(concat('client_region:', c_region))
}
if c_isp {
    say(concat('client_isp:', c_isp))
}
``` |
|Return value|Returns the administrative division code of the specified client in a string. For more information about administrative division codes, see [Administrative division codes](#section_q86_hoc_ph6).|

## client\_isp

Queries the Internet service provider \(ISP\) code of a client. The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|client\_isp\(\)|
|Parameter|N/A|
|Example|```
c_country = client_country()
c_region = client_region()
c_isp = client_isp()
if c_country {
    say(concat('client_country:', c_country))
}
if c_region {
    say(concat('client_region:', c_region))
}
if c_isp {
    say(concat('client_isp:', c_isp))
}
``` |
|Return value|Returns the ISP code of the specified client in a string. ISP codes are:

-   100017: China Telecom
-   100025: China Mobile
-   100026: China Unicom |

## ip\_country

Queries the country code of a specified IP address. The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|ip\_country\(ipaddr\)|
|Parameter|ipaddr: specifies an IP address in dotted decimal notation.|
|Example|```
c_country = ip_country('112.10.80.80')
c_region = ip_region('112.10.80.80')
c_city = ip_city('112.10.80.80')
c_isp = ip_isp('112.10.80.80')
if c_country {
    say(concat('ip_country:', c_country))
}
if c_region {
    say(concat('ip_region:', c_region))
}
if c_city {
    say(concat('ip_city:', c_city))
}
if c_isp {
    say(concat('ip_isp:', c_isp))
}
``` |
|Return value|Returns the country code of the specified IP address in a string. For more information about country codes, see [Country codes](/intl.en-US/EdgeScript/EdgeScript built-in functions/Appendix.md).|

## ip\_region

Queries the administrative division code of the city or province to which a specified IP address belongs. The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|ip\_region\(ipaddr\)|
|Parameter|ipaddr: specifies an IP address in dotted decimal notation.|
|Example|```
c_country = ip_country('112.10.80.80')
c_region = ip_region('112.10.80.80')
c_city = ip_city('112.10.80.80')
c_isp = ip_isp('112.10.80.80')
if c_country {
    say(concat('ip_country:', c_country))
}
if c_region {
    say(concat('ip_region:', c_region))
}
if c_city {
    say(concat('ip_city:', c_city))
}
if c_isp {
    say(concat('ip_isp:', c_isp))
}
``` |
|Return value|Returns the administrative division code of the city or province to which the specified IP address belongs in a string. For more information about administrative division codes, see [Administrative division codes](#section_q86_hoc_ph6).|

## ip\_isp

Queries the ISP code of a specified IP address. The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|ip\_isp\(ipaddr\)|
|Parameter|ipaddr: specifies an IP address in dotted decimal notation.|
|Example|```
c_country = ip_country('112.10.80.80')
c_region = ip_region('112.10.80.80')
c_city = ip_city('112.10.80.80')
c_isp = ip_isp('112.10.80.80')
if c_country {
    say(concat('ip_country:', c_country))
}
if c_region {
    say(concat('ip_region:', c_region))
}
if c_city {
    say(concat('ip_city:', c_city))
}
if c_isp {
    say(concat('ip_isp:', c_isp))
}
``` |
|Return value|Returns the ISP code of the specified IP address in a string. ISP codes are:

-   100017: China Telecom
-   100025: China Mobile
-   100026: China Unicom |

## req\_uri

Details about this function:

-   If the pattern parameter is not included in the request, the URI of the request is returned, excluding the parameters.
-   If the pattern parameter is included in the request, the URI of the request is compared with the match conditions.

The following tables describe the details about this function.

|Item|Description|
|----|-----------|
|Syntax|req\_uri\(\[pattern\]\)|
|Parameter|pattern: compared with the match conditions. The following match types are supported: -   Brute-force algorithm: compares the values based on a brute-force algorithm. This is the default match type.
-   Regular expression: compares the values based on a regular expression. |
|Example|```
# req_uri
say(concat('req_uri: ', req_uri()))
if req_uri('/path1/path2') {
    say('req_uri: plain match')
}
if req_uri('re:/path[0-9]/path[0-9]') {
    say('req_uri: regex match')
}
``` |
|Return value|-   If the pattern parameter is not included in the request, the request URI is returned. Data type: string.
-   If the pattern parameter is included in the request and the request matches the match conditions, a value of true is returned. If no condition is matched, a value of false is returned.

Sample return values:

```
Request: /path1/path2?mode=ip   
Response:
req_uri: /path1/path2
req_uri: plain match
req_uri: regex match
``` |

## req\_uri\_basename

Details about this function:

-   Returns the file name in the request URI if the pattern parameter is not included in the request.
-   Compares the file name in the request URI with the match conditions if the pattern parameter is included in the request.

Examples of file names:

-   Example 1: For /document\_detail/30360.html, the file name is 30360.
-   Example 2: For /M604/guopei\_mp4/ZYJY2017BJGL0101/2-1\_g.mp4, the file name is 2-1\_g.
-   Example 3: For /tarball/foo.tar.bz2, the file name is foo.

Details about this function:

|Item|Description|
|----|-----------|
|Syntax|req\_uri\_basename\(\[pattern\]\)|
|Parameter|pattern: compared with the match conditions. The following match types are supported:-   Brute-force algorithm: compares the values based on a brute-force algorithm. This is the default match type.
-   Regular expression: compares the values based on a regular expression. |
|Example|```
# req_uri_basename
basename = req_uri_basename()
say(concat('req_uri_basename: ', basename, ' ', len(basename)))
if req_uri_basename('foo') {
    say('req_uri_basename: plain match')
}
if req_uri_basename('re:^f.*') {
    say('req_uri_basename: regex match')
}
``` |
|Return value|-   Returns the file name in the request URI if the pattern parameter is not included in the request. Data type: string.
-   If the pattern parameter is included in the request and the request matches the match conditions, a value of true is returned. If no condition is matched, a value of false is returned.

Sample return values:

```
Request: /path1/path2/foo.tar.bz2
Response:
req_uri_basename: foo 3
req_uri_basename: plain match
req_uri_basename: regex match
``` |

## req\_uri\_ext

Details about this function:

-   Returns the extension in the request URI if the pattern parameter is not included in the request.
-   Compares the extension in the request URI with the match conditions if the pattern parameter is included in the request.

Examples of extensions:

-   Example 1: For /document\_detail/30360.html, the extension is .html.
-   Example 2: For /M604/guopei\_mp4/ZYJY2017BJGL0101/2-1\_g.mp4, the extension is .mp4.
-   Example 3: For /tarball/foo.tar.bz2, the extension is .tar.bz2.

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|req\_uri\_ext\(\[pattern\]\)|
|Parameter|pattern: compared with the match conditions. The following match types are supported:-   Brute-force algorithm: compares the values based on a brute-force algorithm. This is the default match type.
-   Regular expression: compares the values based on a regular expression. |
|Example|```
# req_uri_ext
ext = req_uri_ext()
say(concat('req_uri_ext: ', ext, ' ', len(ext)))
if req_uri_ext('.tar.bz2') {
    say('req_uri_ext: plain match')
}
if req_uri_ext('re:\.tar\.bz[0-2]') {
    say('req_uri_ext: regex match')
}
``` |
|Return value|-   Returns the extension in the request URI if the pattern parameter is not included in the request. Data type: string.
-   If the pattern parameter is included in the request and the request matches the match conditions, a value of true is returned. If no condition is matched, a value of false is returned.

Sample return values:

```
Request: /path1/path2/foo.tar.bz2
Response:
req_uri_ext: .tar.bz2 8
req_uri_ext: plain match
req_uri_ext: regex match
``` |

## req\_uri\_seg

Details about this function:

-   In response parameters, the segments are separated with forward slashes \(/\).
    -   Returns all segments if the idx parameter is not included in the request.
    -   Returns the segments \(including the index\) that follow the specified index if the idx parameter is included in the request.
-   Indexes for paragraphs: the index starts from 1 and increases from the leftmost index when more paragraphs are added.
-   Paragraph limit: A paragraph can contain up to 128 characters in length. Characters that exceed this limit are dropped.

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|req\_uri\_seg\(\[idx\]\)|
|Parameter|idx: specifies the start index. This parameter is optional.|
|Example|```
# req_uri_seg
def echo_each(k, v, u) {
    say(concat(get(u, 'msg'), ' : segs[', k, ']=', v))
}
# fetch all segments
segs = req_uri_seg()
foreach(segs, echo_each, ['msg'='req_uri_seg()'])
# fetch segments from idx 3
segs = req_uri_seg(3)
if get(segs, 3) {
    say(concat('req_uri_seg(3): segs[3]=', get(segs, 3)))
}
if get(segs, 4) {
    say(concat('req_uri_seg(3): segs[4]=', get(segs, 4)))
}
if get(segs, 5) {
    say(concat('req_uri_seg(3): segs[5]=', get(segs, 5)))
}
``` |
|Return value|Data type: dictionary. The relevant paragraphs are included. **Note:** When the function retrieves the paragraph from the returned dictionary based on the specified index, the function checks whether the paragraph is empty.

Sample return values:

```
Request: /path1/path2/path3/path4?mode=req2
Response:
req_uri_seg() : segs[1]=path1
req_uri_seg() : segs[2]=path2
req_uri_seg() : segs[3]=path3
req_uri_seg() : segs[4]=path4
req_uri_seg(3): segs[3]=path3
req_uri_seg(3): segs[4]=path4
``` |

## req\_uri\_arg

Queries the value of a specified parameter. If the pattern parameter is included in the request, the value of the specified parameter is compared with the match conditions. The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|req\_uri\_arg\(name, \[pattern\]\)|
|Parameter|-   name: the name of the parameter.

Replace hyphens \(-\) in the parameter name with underscores \(\_\). For example, X-USER-ID must be changed to x\_user\_id.

-   pattern: compared with the match conditions. The following match types are supported:
    -   Brute-force algorithm: compares the values based on a brute-force algorithm. This is the default match type.
    -   Regular expression: compares the values based on a regular expression. |
|Example|```
# req_uri_arg
uid = req_uri_arg('uid')
if uid {
    say(concat('found uid ', uid))
} else {
    say('not found uid')
}
uid_chk = req_uri_arg('uid', '058334')
if uid_chk {
    say('check uid ok. plain mode')
} else {
    say('check uid fail. plain mode')
}
uid_chk = req_uri_arg('uid', 're:[0-9]+')
if uid_chk {
    say('check uid ok. regex mode')
} else {
    say('check uid fail. regex mode')
}
``` |
|Return value|-   If the pattern parameter is not included in the request
    -   The specified parameter exists: returns the value of the parameter specified by the name parameter in a string.
    -   The specified parameter does not exist: returns a value of false.
-   If the pattern parameter is included in the request
    -   The specified parameter exists: returns a value of true if the value matches the match conditions. Otherwise, a value of false is returned.
    -   The specified parameter does not exist: returns a value of false.

Sample return values:

```
Request: /path1/path2/path3/path4?mode=req4&uid
Response:
not found uid
check uid fail. plain mode
check uid fail. regex mode

Request: /path1/path2/path3/path4?mode=req4&uid=
Response:
found uid
check uid fail. plain mode
check uid fail. regex mode

Request: /path1/path2/path3/path4?mode=req4&uid=12345
Response:
found uid 12345
check uid fail. plain mode
check uid ok. regex mode
``` |

## req\_uri\_query\_string

Details about this function:

-   If the pattern parameter is not included in the request, the parameters in the request are returned, excluding the question mark \(?\).
-   If the pattern parameter is included in the request, the parameters in the requests are compared with the match conditions.

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|req\_uri\_query\_string\(\[pattern\]\)|
|Parameter|pattern: compared with the match conditions. The following match types are supported:-   Brute-force algorithm: compares the values based on a brute-force algorithm. This is the default match type.
-   Regular expression: compares the values based on a regular expression. |
|Example|```
# req_uri_query_string
say(concat('req_uri_query_string: ', req_uri_query_string()))
if req_uri_query_string('mode=') {
    say('check uri query string ok. plain mode')
} else {
    say('check uri query string fail. plain mode')
}
if req_uri_query_string('re:mode=[0-9a-z]+') {
    say('check uri query string ok. regex mode')
} else {
    say('check uri query string fail. regex mode')
}
``` |
|Return value|-   Returns the parameters in the request if the pattern parameter is not included in the request. Data type: string.
-   If the pattern parameter is included in the request and the request matches the match conditions, a value of true is returned. If no condition is matched, a value of false is returned.

Sample return values:

```
Request: /path1/path2/path3/path4?mode=req5&token=34Deasd#243
Response:
req_uri_query_string: mode=req5&token=34Deasd
check uri query string fail. plain mode
check uri query string ok. regex mode
``` |

## req\_scheme

Details about this function:

-   Returns the request scheme if the pattern parameter is not included in the request.
-   Compares the request scheme with the match conditions if the pattern parameter is included in the request.

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|req\_scheme\(\[pattern\]\)|
|Parameter|pattern: compared with the match conditions. The following match types are supported:-   Brute-force algorithm: compares the values based on a brute-force algorithm. This is the default match type.
-   Regular expression: compares the values based on a regular expression. |
|Example|```
# req_scheme
say(concat('req_scheme: ', req_scheme()))
if req_scheme('https') {
    say('check scheme ok. plain mode')
} else {
    say('check scheme fail. plain mode')
}
if req_scheme('re:https?') {
    say('check scheme ok. regex mode')
} else {
    say('check scheme fail. regex mode')
}
``` |
|Return value|-   Returns the request scheme if the pattern parameter is not included in the request. Data type: string.
-   If the pattern parameter is included in the request and the request matches the match conditions, a value of true is returned. If no condition is matched, a value of false is returned.

Sample return values:

```
Request: http://xx..
req_scheme: http
check scheme fail. plain mode
check scheme ok. regex mode
``` |

## req\_method

Details about this function:

-   Returns the request method if the pattern parameter is not included in the request.
-   Compares the request method with the match conditions if the pattern parameter is included in the request.

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|req\_method\(\[pattern\]\)|
|Parameter|pattern: compared with the match conditions. The following match types are supported:-   Brute-force algorithm: compares the values based on a brute-force algorithm. This is the default match type.
-   Regular expression: compares the values based on a regular expression. |
|Example|```
# req_method
say(concat('req_method: ', req_method()))
if req_method('GET') {
    say('check method ok. plain mode')
} else {
    say('check method fail. plain mode')
}
if req_method('re:(GET|POST)') {
    say('check method ok. regex mode')
} else {
    say('check method fail. regex mode')
}
``` |
|Return value|-   Returns the request method if the pattern parameter is not included in the request. Data type: string.
-   If the pattern parameter is included in the request and the request matches the match conditions, a value of true is returned. If no condition is matched, a value of false is returned.

Sample return values:

```
Request: POST /xxxx/xxx
Response:
req_method: POST
check method fail. plain mode
check method ok. regex mode
``` |

## req\_host

Details about this function:

-   Returns the value of the Host request header if the pattern parameter is not included in the request.
-   Compares the value of the Host request header with the match conditions if the pattern parameter is included in the request.

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|req\_host\(\[pattern\]\)|
|Parameter|pattern: compared with the match conditions. The following match types are supported:-   Brute-force algorithm: compares the values based on a brute-force algorithm. This is the default match type.
-   Regular expression: compares the values based on a regular expression. |
|Example|```
# req_host
say(concat('req_host: ', req_host()))
if req_host('x.y.z.com') {
    say('check host ok. plain mode')
} else {
    say('check host fail. plain mode')
}
if req_host('re:.+\.y\.z\.com') {
    say('check host ok. regex mode')
} else {
    say('check host fail. regex mode')
}
``` |
|Return value|-   Returns the value of the Host request header if the pattern parameter is not included in the request. Data type: string.
-   If the pattern parameter is included in the request and the request matches the match conditions, a value of true is returned. If no condition is matched, a value of false is returned.

Sample return values:

```
Request: Host: x2.y.z.com
Response:
req_host: x2.y.z.com
check host fail. plain mode
check host ok. regex mode
``` |

## req\_user\_agent

Details about this function:

-   Returns the value of the User-Agent request header if the pattern parameter is not included in the request.
-   Compares the value of the User-Agent request header with the match conditions if the pattern parameter is included in the request.

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|req\_user\_agent\(\[pattern\]\)|
|Parameter|pattern: compared with the match conditions. The following match types are supported:-   Brute-force algorithm: compares the values based on a brute-force algorithm. This is the default match type.
-   Regular expression: compares the values based on a regular expression. |
|Example|```
# req_user_agent
say(concat('req_user_agent: ', req_user_agent()))
if req_user_agent('Mozilla') {
    say('check user_agent ok. plain mode')
} else {
    say('check user_agent fail. plain mode')
}
if req_user_agent('re:^Mozilla') {
    say('check user_agent ok. regex mode')
} else {
    say('check user_agent fail. regex mode')
}
``` |
|Return value|-   Returns the value of the User-Agent request header if the pattern parameter is not included in the request. Data type: string.
-   If the pattern parameter is included in the request and the request matches the match conditions, a value of true is returned. If no condition is matched, a value of false is returned.

Sample return values:

```
ua: specifies user agents. Mozilla/5.0 (Windows NT 10.0; Win64; x64)
Response:
req_user_agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64)
check user_agent fail. plain mode
check user_agent ok. regex mode
``` |

## req\_referer

Details about this function:

-   Returns the value of the Referer request header if the pattern parameter is not included in the request.
-   Compares the value of the Referer request header with the match conditions if the pattern parameter is included in the request.

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|req\_referer\(\[pattern\]\)|
|Parameter|pattern: compared with the match conditions. The following match types are supported:-   Brute-force algorithm: compares the values based on a brute-force algorithm. This is the default match type.
-   Regular expression: compares the values based on a regular expression. |
|Example|```
# req_referer
say(concat('req_referer: ', req_referer()))
if req_referer('https://foo.bar.cn/******00003') {
    say('check referer ok. plain mode')
} else {
    say('check referer fail. plain mode')
}
if req_referer('re:https://foo\.bar\.cn/\*+[0-9]+') {
    say('check referer ok. regex mode')
} else {
    say('check referer fail. regex mode')
}
``` |
|Return value|-   Returns the value of the Referer request header if the pattern parameter is not included in the request. Data type: string.
-   If the pattern parameter is included in the request and the request matches the match conditions, a value of true is returned. If no condition is matched, a value of false is returned.

Sample return values:

```
Request: Referer: https://foo.bar.cn/******00003
Response:
req_referer: https://foo.bar.cn/******00003
check referer ok. plain mode
check referer ok. regex mode
``` |

## req\_cookie

Queries the value of a specified cookie. If the pattern parameter is included in the request, the value of the specified cookie is compared with the match conditions. The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|req\_cookie\(name, \[pattern\]\)|
|Parameter|-   name: specifies the name of the cookie.

Replace hyphens \(-\) in the cookie name with underscores \(\_\). For example, X-USER-ID must be changed to x\_user\_id.

-   pattern: compared with the match conditions. The following match types are supported:
    -   Brute-force algorithm: compares the values based on a brute-force algorithm. This is the default match type.
    -   Regular expression: compares the values based on a regular expression. |
|Example|```
# req_cookie
uid = req_cookie('uid')
if uid {
    say(concat('found cookie uid ', uid))
} else {
    say('not found cookie uid')
}
uid_chk = req_cookie('uid', '058334')
if uid_chk {
    say('check cookie uid ok. plain mode')
} else {
    say('check cookie uid fail. plain mode')
}
uid_chk = req_cookie('uid', 're:^[0-9]+')
if uid_chk {
    say('check cookie uid ok. regex mode')
} else {
    say('check cookie uid fail. regex mode')
}
``` |
|Return value|-   If the pattern parameter is not included in the request
    -   The specified cookie exists: returns the value of the cookie specified by the name parameter in a string.
    -   The specified parameter does not exist: returns a value of false.
-   If the pattern parameter is included in the request
    -   The specified parameter exists: returns a value of true if the value matches the match conditions. Otherwise, a value of false is returned.
    -   The specified parameter does not exist: returns a value of false.

Sample return values:

```
Request: Cookie: uid=123456; token=value2
Response:
found cookie uid 123456
check cookie uid fail. plain mode
check cookie uid ok. regex mode
``` |

## req\_first\_x\_forwarded

Details about this function:

-   Returns the first address in the X-Forwarded-For request header if the pattern parameter is not included in the request.
-   Compares the first address in the X-Forwarded-For request header with the match conditions if the pattern parameter is included in the request.

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|req\_first\_x\_forwarded\_addr\(\[pattern\]\)|
|Parameter|pattern: compared with the match conditions. The following match types are supported:-   Brute-force algorithm: compares the values based on a brute-force algorithm. This is the default match type.
-   Regular expression: compares the values based on a regular expression. |
|Example|```
# req_first_x_forwarded
say(concat('req_first_x_forwarded: ', req_first_x_forwarded()))
if req_first_x_forwarded('1.1.1.1') {
    say('check first_x_forwarded ok. plain mode')
} else {
    say('check first_x_forwarded fail. plain mode')
}
if req_first_x_forwarded('re:1.1.1.[0-9]') {
    say('check first_x_forwarded ok. regex mode')
} else {
    say('check first_x_forwarded fail. regex mode')
}
``` |
|Return value|-   Returns the first address in the X-Forwarded-For request header if the pattern parameter is not included in the request. Data type: string.
-   If the pattern parameter is included in the request and the request matches the match conditions, a value of true is returned. If no condition is matched, a value of false is returned.

Sample return values:

```
Request: X-Forwarded-For: 1.1.1.1, 2.2.2.2, 3.3.3.3
Response:
req_first_x_forwarded: 1.1.1.1
check first_x_forwarded ok. plain mode
check first_x_forwarded ok. regex mode
``` |

## req\_header

Queries the value of a specified request header. If the pattern parameter is included in the request, the value of the specified request header is compared with the match conditions. The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|req\_header\(name, \[pattern\]\)|
|Parameter|-   name: specifies the name of the request header.

Replace hyphens \(-\) in the request header with underscores \(\_\). For example, X-USER-ID must be changed to x\_user\_id.

-   pattern: compared with the match conditions. The following match types are supported:
    -   Brute-force algorithm: compares the values based on a brute-force algorithm. This is the default match type.
    -   Regular expression: compares the values based on a regular expression. |
|Example|```
# req_header
uid = req_header('x_uid')
if uid {
    say(concat('found header x-uid ', uid))
} else {
    say('not found header x-uid')
}
uid_chk = req_header('x_uid', 'es developer')
if uid_chk {
    say('check header x-uid ok. plain mode')
} else {
    say('check header x-uid fail. plain mode')
}
uid_chk = req_header('x_uid', 're:es [a-z]+')
if uid_chk {
    say('check header x-uid ok. regex mode')
} else {
    say('check header x-uid fail. regex mode')
}
``` |
|Return value|-   If the pattern parameter is not included in the request
    -   The specified request header exists: returns the value of the specified request header specified by the name parameter in a string.
    -   The specified parameter does not exist: returns a value of false.
-   If the pattern parameter is included in the request
    -   The specified parameter exists: returns a value of true if the value matches the match conditions. Otherwise, a value of false is returned.
    -   The specified parameter does not exist: returns a value of false.

Sample return values:

```
Request: X-UID: es developer
Response:
found header x-uid es developer
check header x-uid ok. plain mode
check header x-uid ok. regex mode
``` |

## req\_id

Queries the Eagle Eye ID of a request. Each Eagle Eye ID uniquely identifies a request. The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|req\_id\(\)|
|Parameter|N/A|
|Example|```
# req_id
say(concat('req_id: ', req_id()))
``` |
|Return value|Returns the request ID in a string. The return value in this example is `req_id: 6451c43d15815890089411000e`.|

## Administrative division codes

|Administrative division code|City/Province|Administrative division code|City/Province|Administrative division code|City/Province|
|----------------------------|-------------|----------------------------|-------------|----------------------------|-------------|
|370000|Shandong|450000|Guangxi|310000|Shanghai|
|230000|Heilongjiang|540000|Tibet|440000|Guangdong|
|120000|Tianjin|150000|Inner Mongolia|340000|Anhui|
|330000|Zhejiang|530000|Yunnan|630000|Qinghai|
|320000|Jiangsu|620000|Gansu|420000|Hubei|
|410000|Henan|360000|Jiangxi|210000|Liaoning|
|640000|Ningxia|110000|Beijing|460000|Hainan|
|130000|Hebei|510000|Sichuan|500000|Chongqing|
|610000|Shaanxi|220000|Jilin|140000|Shanxi|
|650000|Xinjiang|350000|Fujian|430000|Hunan|
|520000|Guizhou|810000|Hong Kong \(China\)|820000|Macau \(China\)|
|710000|Taiwan \(China\)|N/A|N/A|N/A|N/A|

