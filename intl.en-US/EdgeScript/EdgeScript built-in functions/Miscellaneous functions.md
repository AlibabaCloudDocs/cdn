# Miscellaneous functions

This topic describes the syntax, description, parameters, and return values of Miscellaneous functions. This topic also provides examples of these functions.

## base64\_enc

The following table describes the details about this function.

|Item|Description |
|----|------------|
|Syntax|`base64_enc(s [, no_padding])`|
|Description|Encodes a string in Base64.|
|Parameter|-   s: the string that you want to encode.
-   no\_padding: specifies whether to pad the string. A value of `true` specifies that the string is not padded. Default value: `false`. |
|Return value|Returns a Base64-encoded string.|
|Example|```
if $http_data {
   decdata = base64_dec($http_data)
   say(concat('base64_decdata=', decdata))
   say(concat('base64_encdata=', base64_enc('hello, dsl'))) 
}

Request header: "data: aGVsbG8sIGRzbA=="
Response: base64_decdata=hello, dsl
base64_encdata=aGVsbG8sIGRzbA==
``` |

## base64\_dec

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`base64_dec(s)`|
|Description|Decodes a Base64-encoded string.|
|Parameter|s: the string that you want to decode.|
|Return value|Returns a decoded raw string.|
|Example|```
if $http_data {
   decdata = base64_dec($http_data)
   say(concat('base64_decdata=', decdata))
   say(concat('base64_encdata=', base64_enc('hello, dsl'))) 
}

Request header: "data: aGVsbG8sIGRzbA=="
Response: base64_decdata=hello, dsl
base64_encdata=aGVsbG8sIGRzbA==
``` |

## url\_escape

The following table describes the details about this function.

|Item|Description |
|----|------------|
|Syntax|`url_escape(s)`|
|Description|Uses URL encoding to encode a string.|
|Parameter|s: the string that you want to encode.|
|Return value|Returns a URL-encoded string.|
|Example|```
raw = '/abc/123/ dd/file.m3u8'
esdata = url_escape(raw)
dsdata = url_unescape(esdata)
if eq(raw, dsdata) {
    say(concat('raw=', raw))
    say(concat('dsdata=', dsdata))
}
Output: raw=/abc/123/ dd/file.m3u8
esdata=%2Fabc%2F123%2F%20dd%2Ffile.m3u8
dsdata=/abc/123/ dd/file.m3u8
``` |

## url\_unescape

The following table describes the details about this function.

|Item|Description |
|----|------------|
|Syntax|`url_unescape(s)`|
|Description|Decodes a URL-encoded string.|
|Parameter|s: the string that you want to decode.|
|Return value|Returns a decoded raw string.|
|Example|```
raw = '/abc/123/ dd/file.m3u8'
esdata = url_escape(raw)
dsdata = url_unescape(esdata)
if eq(raw, dsdata) {
    say(concat('raw=', raw))
    say(concat('dsdata=', dsdata))
}
Output: raw=/abc/123/ dd/file.m3u8
esdata=%2Fabc%2F123%2F%20dd%2Ffile.m3u8
dsdata=/abc/123/ dd/file.m3u8
``` |



## rand

The following table describes the details about this function.

|Item|Description |
|----|------------|
|Syntax|`rand(n1, n2)`|
|Description|Generates and returns a random number. Value values: n1 <= returned number <= n2. The n1 parameter specifies the smallest number. The n2 parameter specifies the greatest number.|
|Parameter|-   n1: the smallest number.
-   n2: the greatest number. |
|Return value|Returns a random number.|
|Example|```
r = rand(1,100)
``` |

## rand\_hit

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`rand_hit(ratio)`|
|Description|Retrieves a value of true or false based on the specified probability.|
|Parameter|ratio: the probability. Valid values: 0 to 100.|
|Return value|Returns `true` or false based on the specified probability. If you set ratio to 100, `true` is returned. If you set ratio to 0, `false` is returned.|
|Example|```
rand_hit(80)
``` |

## crc

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`crc(s)`|
|Description|Calculates a Cyclic Redundancy Check \(CRC\) value.|
|Parameter|s: the string for which you want to calculate a CRC digest.|
|Return value|Returns the CRC value of the string specified by the `s` parameter.|
|Example|```
crc('hello edgescript')
``` |

## tonumber

The following table describes the details about this function.

|Item|Description |
|----|------------|
|Syntax|`tonumber(s [, base])`|
|Description|Converts a string to the numeric type.|
|Parameter|-   s: the string that you want to convert.
-   base: the positional notation that you want to use to convert the string. Valid values: 10 and 16. Default value: 10. |
|Example|```
n = tonumber('100')
say(concat('tonumber()=', n))

Output: tonumber()=100
``` |

## base64\_enc\_safe

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`base64_enc_safe(str)`|
|Description|Encodes a string in Base64. In the encoded string, plus signs \(+\) are replaced by minus signs \(-\), forward slashes are replaced by underscores \(\_\), and equal signs \(=\) are removed.|
|Parameter|str: the string that you want to encode.|
|Return value|Returns a decoded raw string.|
|Example|```
add_rsp_header('X-RESPOND-OUTPUT', concat('base64_enc_safe=', base64_enc_safe('hello, dsl')), true)
```

Response header:```
X-RESPOND-OUTPUT: base64_enc_safe=aGVsbG8sIGRzbA
``` |

## base64\_dec\_safe

The following table describes the details about this function.

|Item|Description |
|----|------------|
|Syntax|`base64_dec_safe(str)`|
|Description|Decodes a Base64-encoded string. In the decoded string, minus signs \(-\) are replaced by plus signs \(+\) and underscores \(\_\) are replaced by forward slashes \(/\). Equal signs \(=\) are added to the end of the string to ensure that the string is padded to a multiple of four characters.|
|Parameter|str: the Base64-encoded string that you want to decode.|
|Return value|Returns a decoded raw string.|
|Example|```
add_rsp_header('X-RESPOND-OUTPUT', concat('base64_dec_safe=', base64_dec_safe(base64_enc_safe('hello, dsl'))), true)
```

Response header:```
X-RESPOND-OUTPUT:base64_dec_safe=hello, dsl
``` |

## randomseed

The following table describes the details about this function.

|Item|Description |
|----|------------|
|Syntax|`randomseed()`|
|Description|Generates a random seed.|
|Parameter|None.|
|Return value|None.|
|Example|```
randomseed()
r = rand(1,100)
``` |

