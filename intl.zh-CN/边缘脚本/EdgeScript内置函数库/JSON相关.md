# JSON相关

本文为您介绍JSON相关函数的语法、说明、参数、返回值和示例。

## json\_enc

函数详细信息，请参见下表：

|项目|描述|
|--|--|
|语法|`json_enc(d)`。|
|说明|JSON编码。|
|参数|d：待编码的字典对象。|
|返回值|成功返回编码后的字符串，失败返回`false`。|
|示例|```
var_a = []
var_b = ['v1', 'v2']
set(var_a, 'k1', 'v1')
set(var_a, 'k2', var_b)
var_c = '{"k1":"v1","k2":["v1","v2"]}'
say(concat('json_enc=', json_enc(var_a)))
say(concat('json_dec=', get(json_dec(var_c), 'k1')))

输出：
json_enc={"k1":"v1","k2":["v1","v2"]}
json_dec=v1
``` |

## json\_dec

函数详细信息，请参见下表：

|项目|描述|
|--|--|
|语法|`json_dec(s)`。|
|说明|JSON解码。|
|参数|s：待解码的JSON格式字符串。|
|返回值|成功返回解码后的字典，失败返回`false`。|
|示例|```
var_a = []
var_b = ['v1', 'v2']
set(var_a, 'k1', 'v1')
set(var_a, 'k2', var_b)
var_c = '{"k1":"v1","k2":["v1","v2"]}'
say(concat('json_enc=', json_enc(var_a)))
say(concat('json_dec=', get(json_dec(var_c), 'k1')))

输出：
json_enc={"k1":"v1","k2":["v1","v2"]}
json_dec=v1
``` |

