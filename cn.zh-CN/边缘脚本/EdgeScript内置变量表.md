# EdgeScript内置变量表

本文为您介绍EdgeScript脚本中所有内置变量的含义和对应nginx原生变量。

EdgeScript内置变量如下表所示。

|内置变量名|含义|对应nginx原生变量|
|-----|--|-----------|
|$arg\_\{name\}|`Query String`中的参数`name`值。`Query String`表示HTTP请求中的请求参数。|$arg\_ **说明：** `{name}`中出现的连接号（-），需要使用下划线（\_）替代，例如：`X-USER-ID`对应为`$arg_x_user_id`。 |
|$http\_\{name\}|请求头中的name值。|$http\_ **说明：** `{name}`中出现的连接号（-），需要使用下划线（\_）替代，例如：`X-USER-ID`对应为`$http_x_user_id`。 |
|$cookie\_\{name\}|请求cookie头中的name值。|$cookie\_ **说明：** `{name}`中出现的连接号（-），需要使用下划线（\_）替代，例如：`X-USER-ID`对应为`$cookie_x_user_id`。 |
|$scheme|协议类型。|$scheme|
|$server\_protocol|协议版本。|$server\_protocol|
|$host|原始host。|$host|
|$uri|原始URI。|无|
|$args|`$args`表示当前HTTP请求的全部请求参数，但不包含问号（`?`）。例如：`http://www.a.com/1k.file?k1=v1&k2=v2`。 -   `$arg_k1`可以获得对应的`v1`值。
-   `$args`可以获得整个请求参数字符串，即`k1=v1&k2=v2`，不包括问号（`?`）。

|$args|
|$request\_method|请求方法。|$request\_method|
|$request\_uri|`uri+'?'+args`的内容。|$request\_uri|
|$remote\_addr|客户的IP地址。|$remote\_addr|

**说明：**

-   内置变量名前的美元符号（`$`）仅为强调其内置变量属性，删除后不影响使用。
-   内置变量不允许担当左值，即内置变量不允许被赋值。
-   每条ES规则中最多支持使用200个全局变量，局部变量不限。如果全局变量超过200个请自定义函数，并在函数中以局部变量的形式使用全局变量。

