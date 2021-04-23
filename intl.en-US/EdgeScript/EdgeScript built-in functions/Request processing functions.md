# Request processing functions

This topic describes the syntax, description, parameters, and return values of request processing functions. This topic also provides examples of these functions.

## add\_req\_header

The following table describes the details about this function.

|Item|Description |
|----|------------|
|Syntax|`add_req_header(name, value [, append])`|
|Description|Adds a request header to requests before they are redirected to the origin server.|
|Parameter|-   `name`: the name of the request header that you want to add. Data type: string.
-   `value`: the value of the request header that you want to add. Data type: string.
-   `append`: specifies whether to append a request header with the specified `value` if a request header with the same name already exists. Valid values: true and false. Default value: false. Data type: Boolean. If you set this parameter to false, the specified value will overwrite the value of the existing request header. |
|Return value|Returns `true` by default and returns `false` if the specified request header is invalid.|
|Example|```
add_req_header('USER-DEFINED-REQ-1', '1')
add_req_header('USER-DEFINED-REQ-1', 'x', true)
add_req_header('USER-DEFINED-REQ-2', '2')
del_req_header('USER-DEFINED-REQ-2')

Note: The following request headers are added:
USER-DEFINED-REQ-1: 1
USER-DEFINED-REQ-1: x

The USER-DEFINED-REQ-2 header is added and then deleted. Therefore, the USER-DEFINED-REQ-2 request header is not included in requests that are redirected to the origin server.
``` |

## del\_req\_header

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`del_req_header(name)`|
|Description|Deletes a request header from requests before they are redirected to the origin server.|
|Parameter|`name`: the name of the request header that you want to delete. Data type: string.|
|Return value|Returns `true` by default and returns `false` if the specified request header is invalid.|
|Example|```
add_req_header('USER-DEFINED-REQ-1', '1')
add_req_header('USER-DEFINED-REQ-1', 'x', true)
add_req_header('USER-DEFINED-REQ-2', '2')
del_req_header('USER-DEFINED-REQ-2')

Note: The following request headers are added:
USER-DEFINED-REQ-1: 1
USER-DEFINED-REQ-1: x

The USER-DEFINED-REQ-2 header is added and then deleted. Therefore, the USER-DEFINED-REQ-2 request header is not included in requests that are redirected to the origin server.
``` |

## add\_rsp\_header

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`add_rsp_header(name, value [, append])`|
|Description|Adds a response header.|
|Parameter|-   `name`: the name of the response header that you want to add. Data type: string.
-   `value`: the value of the response header that you want to add. Data type: string.

You can specify one of the following expressions for the `value` parameter to enable the value to be dynamically replaced in the response phase:

    -   $\{x\}: replaced with the value of `ngx.var.x`.
    -   @\{y\}: replaced with the value of `response header y`.
-   `append`: specifies whether to append a response header with the specified `value` if a response header with the same name already exists. Valid values: true and false. Default value: false. Data type: Boolean. If you set this parameter to false, the specified value will overwrite the value of the existing response header. |
|Return value|Returns `true` by default and returns `false` if the specified response header is invalid.|
|Example|```
add_rsp_header('USER-DEFINED-RSP-1', '1')
add_rsp_header('USER-DEFINED-RSP-1', 'x', true)
add_rsp_header('USER-DEFINED-RSP-2', '2')
del_rsp_header('USER-DEFINED-RSP-2')

Note: The following response headers are added:
USER-DEFINED-RSP-1: 1
USER-DEFINED-RSP-1: x

The USER-DEFINED-RSP-2 header is added and then deleted. Therefore, the USER-DEFINED-RSP-2 header is not included in the responses.
``` |

## del\_rsp\_header

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`del_rsp_header(name)`|
|Description|Deletes a response header.|
|Parameter|`name`: the name of the response header that you want to delete. Data type: string.|
|Return value|Returns `true` by default and returns `false` if the specified response header is invalid.|
|Example|```
add_rsp_header('USER-DEFINED-RSP-1', '1')
add_rsp_header('USER-DEFINED-RSP-1', 'x', true)
add_rsp_header('USER-DEFINED-RSP-2', '2')
del_rsp_header('USER-DEFINED-RSP-2')

The following response headers are added:
USER-DEFINED-RSP-1: 1
USER-DEFINED-RSP-1: x

The USER-DEFINED-RSP-2 header is added and then deleted. Therefore, the USER-DEFINED-RSP-2 header is not included in the responses.
``` |

## encode\_args

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`encode_args(d)`|
|Description|Converts the `k/v` pairs in the dictionary specified by `d` to a URI-encoded string in the format of k1=v1&k2=v2.|
|Parameter|d: the dictionary that you want to convert.|
|Return value|Returns a URI-encoded string.|
|Example|```
my_args = []
set(my_args, 'signature', 'da9dc4b7-87ae-4330-aaaf-e5454e2c2af1')
set(my_args, 'algo', 'private sign1')
my_args_str = encode_args(my_args)
add_rsp_header('X-DSL-ENCODE-ARGS', my_args_str)

to_args = decode_args(my_args_str)
if get(to_args, 'algo') {
    add_rsp_header('X-DSL-DECODE-ARGS-ALGO', get(to_args, 'algo'))
}
if get(to_args, 'signature') {
    add_rsp_header('X-DSL-DECODE-ARGS-SIGN', get(to_args, 'signature'))
}

Output: The following response headers are added:
X-DSL-ENCODE-ARGS: signature=da9dc4b7-87ae-4330-aaaf-e5454e2c2af1&algo=private%20sign1
X-DSL-DECODE-ARGS-ALGO: private sign1
X-DSL-DECODE-ARGS-SIGN: da9dc4b7-87ae-4330-aaaf-e5454e2c2af1
``` |

## decode\_args

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`decode_args(s)`|
|Description|Converts a URI-encoded string in the format of k1=v1&k2=v2 to a string of dictionary type.|
|Parameter|s: the string that you want to convert.|
|Return value|Returns a dictionary object converted from the specified string.|
|Example|```
my_args = []
set(my_args, 'signature', 'da9dc4b7-87ae-4330-aaaf-e5454e2c2af1')
set(my_args, 'algo', 'private sign1')
my_args_str = encode_args(my_args)
add_rsp_header('X-DSL-ENCODE-ARGS', my_args_str)

to_args = decode_args(my_args_str)
if get(to_args, 'algo') {
    add_rsp_header('X-DSL-DECODE-ARGS-ALGO', get(to_args, 'algo'))
}
if get(to_args, 'signature') {
    add_rsp_header('X-DSL-DECODE-ARGS-SIGN', get(to_args, 'signature'))
}

Output: The following response headers are added:
X-DSL-ENCODE-ARGS: signature=da9dc4b7-87ae-4330-aaaf-e5454e2c2af1&algo=private%20sign1
X-DSL-DECODE-ARGS-ALGO: private sign1
X-DSL-DECODE-ARGS-SIGN: da9dc4b7-87ae-4330-aaaf-e5454e2c2af1
``` |

## rewrite

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`rewrite(url, flag, code)`|
|Description|Performs a rewrite or redirect operation.|
|Parameter|-   url: the URL to which the source URI is rewritten after the rewrite operation. Data type: string.
    -   If you set the flag parameter to redirect or break, only the URI is rewritten. This parameter specifies the URI after the rewrite operation.
    -   If you set the flag parameter to enhance\_redirect or enhance\_break, the URI and parameters are rewritten. This parameter specifies the URI and parameters after the rewrite operation.
-   flag: the rewrite mode. Data type: string.
    -   redirect: rewrites only the URI. Parameters are not rewritten. By default, a 302 redirect is performed. If you specify this mode, the `code` parameter is configurable. Valid values for the code parameter are 301, 302 \(default\), 303, 307, and 308.
    -   break: rewrites only the URI to a URL. Parameters are not rewritten.
    -   enhance\_redirect: similar to `redirect`. However, both the URI and parameters are rewritten.
    -   enhance\_break: similar to `break`. However, both the URI and parameters are rewritten.
-   code: the HTTP status code. Data type: numeric.

This parameter is available only when you set the flag parameter to redirect or enhance\_redirect. |
|Return value|-   Returns `true` by default for a rewrite operation.
-   Does not return values by default for a redirect operation. |
|Example|```
if and($arg_mode, eq($arg_mode, 'rewrite:enhance_break')) {
    rewrite('/a/b/c.txt?k=v', 'enhance_break')
}
Note: The URI and parameters of requests redirected to the origin server are rewritten to /a/b/c.txt?k=v

if and($arg_mode, eq($arg_mode, 'rewrite:enhance_redirect')) {
    rewrite('/a/b/c.txt?k=v', 'enhance_redirect')
}
if and($arg_mode, eq($arg_mode, 'rewrite:enhance_redirect_301')) {
    rewrite('/a/b/c.txt?k=v', 'enhance_redirect', 301)
}
Note: A 302 or 301 redirect to /a/b/c.txt? is performed.k=v

if and($arg_mode, eq($arg_mode, 'rewrite:break')) {
    rewrite('/a/b/c.txt', 'break')
}
Note: The URI of requests redirected to the origin server is rewritten to /a/b/c.txt and the original parameters in the requests remain unchanged.

if and($arg_mode, eq($arg_mode, 'rewrite:redirect')) {
    rewrite('/a/b/c.txt', 'redirect')
}
if and($arg_mode, eq($arg_mode, 'rewrite:redirect_301')) {
    rewrite('/a/b/c.txt', 'redirect', 301)
}
Note: A 302 or 301 redirect to /a/b/c.txt is performed and the original parameters remain unchanged.
``` |

## say

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`say(arg)`|
|Description|Prints a response body and appends a newline character at the end of the output.|
|Parameter|arg: the content of the response body. Data type: any type.|
|Return value|None.|
|Example|```
say('hello')
print('byebye')
print('byebye')

Output:
hello
byebyebyebye
``` |

## print

The following table describes the details about this function.

|Item|Description |
|----|------------|
|Syntax|`print(arg)`|
|Description|Prints a response body. This function is different from the `say()` function. This function does not append a newline at the end of the output.|
|Parameter|arg: the content of the response body. Data type: any type.|
|Return value|None.|
|Example|```
say('hello')
print('byebye')
print('byebye')

Output:
hello
byebyebyebye
``` |

## exit

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`exit(code [, body])`|
|Description|Ends the current request with the specified `code`. If you also set the `body` parameter, a response that includes the specified response body is returned.|
|Parameter|-   code: the HTTP status code to return.
-   body: the response body. |
|Return value|None.|
|Example|-   Example 1

    ```
if not($arg_key) {
    exit(403)
}
Note: If a request does not include the key parameter, the request is denied and the HTTP 403 status code is returned. 

if not($cookie_user) {
    exit(403, 'not cookie user')
}
Note: If a request does not include cookie_user, the request is denied and a response that contains the body "not cookie user" is returned with the HTTP 403 status code.

if not(0) {
    exit(403)
}
Note: The not(0) function returns a value of false.

if not(false) {
    exit(403)
}
Note: The not(false) function returns a value of true.
    ```

-   Example 2

    ```
pcs = capture_re($request_uri,'^/([^/]+)/([^/]+)([^?]+)\?(.*)')
sec1 = get(pcs, 1)
sec2 = get(pcs, 2)
sec3 = get(pcs, 3)
if or(not(sec1), not(sec2), not(sec3)) {
   add_rsp_header('X-TENGINE-ERROR', 'auth failed - missing necessary uri set')
   exit(403)
}
digest = md5(concat(sec1, sec3))
if ne(digest, sec2) {
    add_rsp_header('X-TENGINE-ERROR', 'auth failed - invalid digest')
    exit(403)
}
    ``` |

