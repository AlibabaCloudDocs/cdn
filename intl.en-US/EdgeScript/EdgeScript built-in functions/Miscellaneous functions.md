# Miscellaneous functions

This topic describes the syntax, description, parameters, return values, and examples of Miscellaneous functions.

## base64\_enc

Details of this function:

-   Syntax: `base64_enc(s [, no_padding])`.
-   Description

    Encodes a string in Base64.

-   Parameters
    -   s: the string that you want to encode.
    -   no\_padding: specifies whether to pad the string. A value of `true` specifies that the string is not padded. A value of `false` specifies that the string is padded. Default value: false.
-   Response parameters

    Returns a Base64-encoded string.

-   Examples

    ```
    if $http_data {
       decdata = base64_dec($http_data)
       say(concat('base64_decdata=', decdata))
       say(concat('base64_encdata=', base64_enc('hello, dsl'))) 
    }
    
    Request header: "data: aGVsbG8sIGRzbA=="
    Response: base64_decdata=hello, dsl
    base64_encdata=aGVsbG8sIGRzbA==
    ```


## base64\_dec

Details of this function:

-   Syntax: `base64_dec(s)`.
-   Description

    Decodes a Base64-encoded string.

-   Parameters

    s: the string that you want to decode.

-   Response parameters

    Returns a decoded raw string.

-   Examples

    ```
    if $http_data {
       decdata = base64_dec($http_data)
       say(concat('base64_decdata=', decdata))
       say(concat('base64_encdata=', base64_enc('hello, dsl'))) 
    }
    
    Request header: "data: aGVsbG8sIGRzbA=="
    Response: base64_decdata=hello, dsl
    base64_encdata=aGVsbG8sIGRzbA==
    ```


## url\_escape

Details of this function:

-   Syntax: `url_escape(s)`.
-   Description

    Encodes a string in URL.

-   Parameters

    s: the string that you want to encode.

-   Response parameters

    Returns a URL-encoded string.

-   Examples

    ```
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
    ```


## url\_unescape

Details of this function:

-   Syntax: `url_unescape(s)`.
-   Description

    Decodes a URL-encoded string.

-   Parameters

    s: the string that you want to decode.

-   Response parameters

    Returns a decoded raw string.

-   Examples

    ```
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
    ```


## rand

Details of this function:

-   Syntax: `rand(n1, n2)`.
-   Description

    Generates and returns a random number. Value values: n1 <= returned number <= n2. The n1 parameter specifies the smallest number. The n2 parameter specifies the greatest number.

-   Parameters
    -   n1: the smallest number.
    -   n2: the greatest number.
-   Response parameters

    Returns a random number.

-   Examples

    ```
    r = rand(1,100)
    ```


## rand\_hit

Details of this function:

-   Syntax: `rand_hit(ratio)`.
-   Description

    Retrieves a value of true or false based on the specified probability.

-   Parameters

    ratio: the probability. Valid values: 0 to 100.

-   Response parameters

    Returns `true` or false based on the specified probability. If you set ratio to 100, `true` is returned. If you set ratio to 0, `false` is returned.

-   Examples

    ```
    rand_hit(80)
    ```


## crc

Details of this function:

-   Syntax: `crc(s)`.
-   Description

    Calculates a Cyclic Redundancy Check \(CRC\) value.

-   Parameters

    s: the string for which you want to calculate a CRC digest.

-   Response parameters

    Returns the CRC value of the string specified by the `s` parameter.

-   Examples

    ```
    crc('hello edgescript')
    ```


## tonumber

Details of this function:

-   Syntax: `tonumber(s [, base])`.
-   Description

    Converts a string to numeric values.

-   Parameters
    -   s: the string that you want to convert.
    -   base: the positional notation that you want to use to convert the string. Valid values: 10 and 16. Default value: 10.
-   Examples

    ```
    n = tonumber('100')
    say(concat('tonumber()=', n))
    
    Output: tonumber()=100
    ```


