# Logical functions

This topic describes the syntax, description, parameters, and return values of logical functions. This topic also provides examples of these functions.

## and

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`and(arg, ...)`|
|Description|-   Executes the AND logical operator.
-   Short-circuit evaluation is supported. When a value evaluates to false, the values that follow this value are not evaluated. |
|Parameter|The value that you want to check. You can specify one or more values. Data type: any type.|
|Return value|Returns `true` if all values evaluate to true and returns `false` if a value evaluates to false.|
|Example|```
if and($arg_mode, eq($arg_mode, 'set_header')) {
    add_rsp_header('USER-DEFINED-1','path1')
}
```

-   a. If the request includes the mode parameter and the value of the mode parameter is set\_header, set the USER-DEFINED-1 response header.
-   b. If the request does not include the mode parameter, the short-circuit evaluation takes effect and the eq comparison operator is not executed. The response header USER-DEFINED-1 will not be set because the and\(\) function returns a value of false. |

## or

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`or(arg, ...)`|
|Description|-   Executes the OR logical operator.
-   Short-circuit evaluation is supported. When a value evaluates to true, the values that follow this value are not evaluated. |
|Parameter|The value that you want to check. You can specify one or more values. Data type: any type.|
|Return value|Returns `true` if a value evaluates to true and returns `false` if all values evaluate to false.|
|Example|```
if and($http_from, or(eq($http_from, 'wap'), eq($http_from, 'comos'))) {
    rewrite(concat('http://tech.com.cn/zt_d/we2015/', $http_from), 'enhance_redirect')
}
```

-   a. If the request includes the From header and its value is wap or comos, the HTTP 302 status code is returned and the request is redirected to http://tech.com.cn/zt\_d/we2015/\[wap\|comos\].
-   b. If the request includes the From header and its value is wap, the short-circuit evaluation takes effect and the comos value is ignored. The or\(\) function returns a value of true. |

## not

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`not(arg)`|
|Description|Executes the NOT logical operator. The values of `undef` and `false` evaluate to false, and other values evaluate to true.|
|Parameter|The value that you want to check. You can specify only one value. Data type: any type.|
|Return value|-   true
-   false |
|Example|```
if not($arg_key) {
    exit(403)
}
if not($cookie_user) {
    exit(403, 'not cookie user')
}
if not(0) {
    exit(403)
}
if not(false) {
    exit(403)
}
```

-   If a request does not include the key parameter, the request is denied and the HTTP 403 status code is returned.
-   If a request does not include cookie\_user, the request is denied. The HTTP 403 status code and the response body "not cookie user" are returned.
-   The not\(0\) function returns a value of false.
-   The not\(false\) function returns a value of true. |

## eq

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`eq(arg1, arg2)`|
|Description|Compares whether two values are equal.|
|Parameter|-   arg1: the first value to compare. Data type: any type.
-   arg2: the second value to compare. Data type: same as the `arg1` parameter. |
|Return value|Returns `true` if the two values are equal and returns `false` if they are not equal.|
|Example|```
key1 = 'value1'
key2 = 'value2'
if and($arg_k1, $arg_k2, eq(key1, $arg_k1), ne(key2, $arg_k2)) {
    say('match condition')
}
```

-   a. If the request includes both the k1 and k2 parameters, the comparison operations are performed.
-   b. If the request does not include the k1 or k2 parameter, the short-circuit evaluation takes effect and the comparison operations are not performed.
-   eq: c. eq: whether the value of the k1 parameter is equal to value1.
-   ne: d. ne: whether the value of the k2 parameter is not equal to value2.
-   e. The response that contains the response body "match condition" is returned only if the following conditions are met: the request includes both the k1 and k2 parameters, the value of the k1 parameter is equal to value1, and the value of the k2 parameter is not equal to value2. |

## ne

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`ne(arg1, arg2)`|
|Description|Compares whether two values are not equal.|
|Parameter|-   arg1: the first value to compare. Data type: any type.
-   arg2: the second value to compare. Data type: same as the `arg1` parameter. |
|Return value|Returns `true` if the two values are not equal and returns `false` if they are equal.|
|Example|```
key1 = 'value1'
key2 = 'value2'
if and($arg_k1, $arg_k2, eq(key1, $arg_k1), ne(key2, $arg_k2)) {
    say('match condition')
}
```

-   a. If the request includes both the k1 and k2 parameters, the comparison operations are performed.
-   b. If the request does not include the k1 or k2 parameter, the short-circuit evaluation takes effect and the comparison operations are not performed.
-   eq: c. eq: whether the value of the k1 parameter is equal to value1.
-   ne: d. ne: whether the value of the k2 parameter is not equal to value2.
-   e. The response that contains the response body "match condition" is returned only if the following conditions are met: the request includes both the k1 and k2 parameters, the value of the k1 parameter is equal to value1, and the value of the k2 parameter is not equal to value2. |

## null

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`null(v)`|
|Description|Checks whether a data type is specified for EdgeScript \(ES\).|
|Parameter|v: the parameter to pass. Data type: array, dictionary, or string. A value of false is returned for other data types.|
|Return value|Data type: Boolean.-   A value of true is returned if the value of v is an array or a dictionary.
-   A value of true is returned if the value of v is an empty string.
-   A value of false is returned if v is set to other data types. |
|Example|```
d = []
say(null(d))
set(d, 1, 'v1')
say(null(d))
say(tostring(null('x')))
say(tostring(null('')))
```

Output:```
true
false
false
true
``` |

