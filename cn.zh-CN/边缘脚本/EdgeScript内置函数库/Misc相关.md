# Misc相关

本文为您介绍Misc相关函数的语法、说明、参数、返回值和示例。

## base64\_enc

函数详细信息，请参见下表：

|项目|描述|
|--|--|
|语法|`base64_enc(s [, no_padding])`。|
|说明|base64编码。|
|参数|-   s：待编码的字符串。
-   no\_padding：`true`表示无填充，默认`false`。 |
|返回值|base64编码后的字符串。|
|示例|```
if $http_data {
   decdata = base64_dec($http_data)
   say(concat('base64_decdata=', decdata))
   say(concat('base64_encdata=', base64_enc('hello, dsl'))) 
}

请求header: "data: aGVsbG8sIGRzbA=="
响应：base64_decdata=hello, dsl
base64_encdata=aGVsbG8sIGRzbA==
``` |

## base64\_dec

函数详细信息，请参见下表：

|项目|描述|
|--|--|
|语法|`base64_dec(s)`。|
|说明|base64解码。|
|参数|s：待解码的字符串。|
|返回值|base64解码后的字符串。|
|示例|```
if $http_data {
   decdata = base64_dec($http_data)
   say(concat('base64_decdata=', decdata))
   say(concat('base64_encdata=', base64_enc('hello, dsl'))) 
}

请求header: "data: aGVsbG8sIGRzbA=="
响应：base64_decdata=hello, dsl
base64_encdata=aGVsbG8sIGRzbA==
``` |

## url\_escape

函数详细信息，请参见下表：

|项目|描述|
|--|--|
|语法|`url_escape(s)`。|
|说明|URL编码。|
|参数|s：待编码的字符串。|
|返回值|URL编码后的字符串。|
|示例|```
raw = '/abc/123/ dd/file.m3u8'
esdata = url_escape(raw)
dsdata = url_unescape(esdata)
if eq(raw, dsdata) {
    say(concat('raw=', raw))
    say(concat('dsdata=', dsdata))
}
输出：raw=/abc/123/ dd/file.m3u8
esdata=%2Fabc%2F123%2F%20dd%2Ffile.m3u8
dsdata=/abc/123/ dd/file.m3u8
``` |

## url\_unescape

函数详细信息，请参见下表：

|项目|描述|
|--|--|
|语法|`url_unescape(s)`。|
|说明|URL解码。|
|参数|s：待解码的字符串。|
|返回值|URL解码后的字符串。|
|示例|```
raw = '/abc/123/ dd/file.m3u8'
esdata = url_escape(raw)
dsdata = url_unescape(esdata)
if eq(raw, dsdata) {
    say(concat('raw=', raw))
    say(concat('dsdata=', dsdata))
}
输出：raw=/abc/123/ dd/file.m3u8
esdata=%2Fabc%2F123%2F%20dd%2Ffile.m3u8
dsdata=/abc/123/ dd/file.m3u8
``` |

函数详细解释如下：

## rand

函数详细信息，请参见下表：

|项目|描述|
|--|--|
|语法|`rand(n1, n2)`。|
|说明|生成随机数，随机数范围：n1 <= 返回值 <= n2。|
|参数|-   n1：随机数下限。
-   n2：随机数上限。 |
|返回值|返回生成的随机数。|
|示例|```
r = rand(1,100)
``` |

## rand\_hit

函数详细信息，请参见下表：

|项目|描述|
|--|--|
|语法|`rand_hit(ratio)`。|
|说明|按指定概率返回真假。|
|参数|ratio：为真概率，有效值范围为\[0-100\]。|
|返回值|按ratio概率返回`true`。例如：当ratio为100时，返回`true`，当ratio为0时，返回`false`。|
|示例|```
rand_hit(80)
``` |

## crc

函数详细信息，请参见下表：

|项目|描述|
|--|--|
|语法|`crc(s)`。|
|说明|计算crc摘要。|
|参数|s：待计算摘要的字符串。|
|返回值|返回`s`的crc摘要。|
|示例|```
crc('hello edgescript')
``` |

## tonumber

函数详细信息，请参见下表：

|项目|描述|
|--|--|
|语法|`tonumber(s [, base])`。|
|说明|类型转换，将字符串类型转换为数字类型。|
|参数|-   s：待转换的字符串。
-   base：可指定目标转换进制，可用值：10和16，默认10进制。 |
|示例|```
n = tonumber('100')
say(concat('tonumber()=', n))

输出：tonumber()=100
``` |

## base64\_enc\_safe

函数详细信息，请参见下表：

|项目|描述|
|--|--|
|语法|`base64_enc_safe(str)`。|
|说明|对输入的字符串进行Base64安全编码。安全编码后输出时，需要将'+'替换'-'，'/'替换成'\_'，同时去掉编码后的'='。|
|参数|str：待加密的字符串。|
|返回值|返回字符串类型|
|示例|```
add_rsp_header('X-RESPOND-OUTPUT', concat('base64_enc_safe=', base64_enc_safe('hello, dsl')), true)
```

输出响应头：```
X-RESPOND-OUTPUT：base64_enc_safe=aGVsbG8sIGRzbA
``` |

## base64\_dec\_safe

函数详细信息，请参见下表：

|项目|描述|
|--|--|
|语法|`base64_dec_safe(str)`。|
|说明|对输入的字符串进行Base64安全解码。安全解码后输出时，需要将'-'替换'+'，'\_'替换'/'，末尾用'='按照4的余数补齐。|
|参数|str：Base64加密后的内容。|
|返回值|返回字符串类型。|
|示例|```
add_rsp_header('X-RESPOND-OUTPUT', concat('base64_dec_safe=', base64_dec_safe(base64_enc_safe('hello, dsl'))), true)
```

输出响应头：```
X-RESPOND-OUTPUT:base64_dec_safe=hello, dsl
``` |

## randomseed

函数详细信息，请参见下表：

|项目|描述|
|--|--|
|语法|`randomseed()`。|
|说明|指定生成随机数种子。|
|参数|无。|
|返回值|无。|
|示例|```
randomseed()
r = rand(1,100)
``` |

