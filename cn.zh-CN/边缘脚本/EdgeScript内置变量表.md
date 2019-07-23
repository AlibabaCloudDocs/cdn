# EdgeScript内置变量表 {#concept_1322635 .concept}

介绍EdgeScript的内置变量表。

EdgeScript内置变量表如下表所示。

|内置变量名|含义|对应nginx原生变量|
|-----|--|-----------|
|$arg\_\{name\}|Query String中的参数name值|$arg\_|
|$http\_\{name\}|请求头中的name值|$http\_|
|$cookie\_\{name\}|请求cookie头中的name值|$cookie\_|
|$scheme|协议类型|$scheme|
|$server\_protocol|协议版本|$server\_protocol|
|$host|原始的host|$host|
|$uri|原始uri| |
|$args|Query String，不含？|$args|
|$request\_method|请求方法|$request\_method|
|$request\_uri|uri+'?'+args的内容|$request\_uri|
|$remote\_addr|客户的ip|$remote\_addr|

**说明：** 

-   内置变量名前的$，仅为强调其内置变量属性，去掉不影响使用。
-   内置变量不允许担当左值，即不允许被赋值。

