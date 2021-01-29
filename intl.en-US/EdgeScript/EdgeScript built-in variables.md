# EdgeScript built-in variables

This topic describes EdgeScript built-in variables and the corresponding NGINX variables.

The following table describes the EdgeScript built-in variables.

|Built-in variable|Description|NGINX variable|
|-----------------|-----------|--------------|
|$arg\_\{name\}|The value of the `name` parameter in the `Query String`. The `Query String` represents request parameters in an HTTP request.|$arg\_ **Note:** Hyphens \(-\) in the `{name}` field must be replaced by underscores \(\_\). For example, `X-USER-ID` must be changed to `$arg_x_user_id`. |
|$http\_\{name\}|The value of the name field in the request header.|$http\_ **Note:** Hyphens \(-\) in the `{name}` field must be replaced by underscores \(\_\). For example, `X-USER-ID` must be changed to `$http_x_user_id`. |
|$cookie\_\{name\}|The value of the name field in the request cookie header.|$cookie\_ **Note:** Hyphens \(-\) in the `{name}` field must be replaced by underscores \(\_\). For example, `X-USER-ID` must be changed to `$cookie_x_user_id`. |
|$scheme|The protocol.|$scheme|
|$server\_protocol|The version of the protocol.|$server\_protocol|
|$host|The original host.|$host|
|$uri|The original URI.|N/A|
|$args|`$args` represents all request parameters in an HTTP request, excluding question marks \(`?`\). For example, the URI of the request is `http://www.a.com/1k.file?k1=v1&k2=v2`. -   `$arg_k1` returns the value of the k1 parameter: `v1`.
-   `$args` is used to return the entire Query String: `k1=v1&k2=v2`. Question marks \(`?`\) are excluded.

|$args|
|$request\_method|The request method.|$request\_method|
|$request\_uri|`uri+'?' + args`.|$request\_uri|
|$remote\_addr|The IP address of the client that sends the request.|$remote\_addr|

**Note:**

-   The dollar sign \(`$`\) before a variable is used to specify that the variable is a built-in variable. You can remove the dollar sign based on your business requirements.
-   Do not assign values to built-in variables in the same way as parameters.
-   You can specify at most 200 global variables and an unlimited number of local variables in a script. To specify more than 200 global variables in a script, create a custom function and use the global variables as local variables in the function.

