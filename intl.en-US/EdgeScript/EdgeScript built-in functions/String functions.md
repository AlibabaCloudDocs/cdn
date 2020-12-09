# String functions

This topic describes the syntax, description, parameters, and response parameters of string functions. This topic also provides examples of these functions.

## substr

Details about this function:

-   Syntax: `substr(s, i, j)`.
-   Description

    Extracts parts from a string.

-   Parameters
    -   s: the string that you want to extract.
    -   i: the position to start extraction in the source string, counting from 1. A value of -1 specifies the rightmost character of the string. Data type: integer.
    -   j: the position to end extraction in the source string, counting from 1. A value of -1 specifies the rightmost character of the string. Data type: integer.
-   Response parameters

    Returns the substring `s[i, j]` of `s`.

-   Examples

    ```
    //The two methods that are used to determine whether a file is an M3U8 file.
    if eq(substr($uri, -5, -1), '.m3u8') {
        say(concat($uri, ' is .m3u8'))
    }
    
    uri_len = len($uri)
    if eq(substr($uri, -5, uri_len), '.m3u8') {
        say(concat($uri, ' is .m3u8'))
    }
    ```


## concat

Details about this function:

-   Syntax: `concat(s1, ...)`.
-   Description

    Concatenates strings.

-   Parameters

    s1: the strings that you want to concatenate. You can specify one or more strings. Numeric values are supported.

-   Response parameters

    Returns the concatenated string.

-   Examples

    ```
    //The two methods that are used to determine whether a file is an M3U8 file.
    if eq(substr($uri, -5, -1), '.m3u8') {
        say(concat($uri, ' is .m3u8'))
    }
    
    uri_len = len($uri)
    if eq(substr($uri, -5, uri_len), '.m3u8') {
        say(concat($uri, ' is .m3u8'))
    }
    ```


## upper

Details about this function:

-   Syntax: `upper(s)`.
-   Description

    Converts a string to uppercase letters.

-   Parameters

    s: the string that you want to convert.

-   Response parameters

    Returns the string specified by the `s` parameter in uppercase letters.

-   Examples

    ```
    //Output:
    //HELLO,DSL
    //hello, dsl
    
    mystr = 'Hello, Dsl'                                                                                                                                                                                   
    say(upper(mystr))                                                                                                                                                                                      
    say(lower(mystr)) 
    ```


## lower

Details about this function:

-   Syntax: `lower(s)`.
-   Description

    Converts a string to lowercase letters.

-   Parameters

    s: the string that you want to convert.

-   Response parameters

    Returns the string specified by the `s` parameter in lowercase letters.

-   Examples

    ```
    //Output:
    //HELLO,DSL
    //hello, dsl
    
    mystr = 'Hello, Dsl'                                                                                                                                                                                   
    say(upper(mystr))                                                                                                                                                                                      
    say(lower(mystr)) 
    ```


## len

Details about this function:

-   Syntax: `len(s)`.
-   Description

    Queries the length of a string.

-   Parameters

    s: the string that you want to measure.

-   Response parameters

    Returns the length of the string specified by the `s` parameter. Data type: integer.

-   Examples

    ```
    //The two methods that are used to determine whether a file is an M3U8 file.
    if eq(substr($uri, -5, -1), '.m3u8') {
        say(concat($uri, ' is .m3u8'))
    }
    
    uri_len = len($uri)
    if eq(substr($uri, -5, uri_len), '.m3u8') {
        say(concat($uri, ' is .m3u8'))
    }
    ```


## byte

Details about this function:

-   Syntax: `byte(c)`.
-   Description

    Queries the ASCII value of a character.

-   Parameters

    c: the character whose ASCII value you want to query. You can specify only one character.

-   Response parameters

    Returns the ASCII value of the specified character. Data type: numeric.

-   Examples

    ```
    //Output: 97
    //65
    
    say(byte('a'))
    say(byte('A'))
    ```


## match\_re

Details about this function:

-   Syntax: `match_re(s, p [, o])`.
-   Description

    Uses the Perl Compatible Regular Expressions \(PCRE\) engine for regular expression matching.

-   Parameters
    -   s: the string that you want to match. Data type: string.
    -   p: the regular expression. Data type: string.
    -   o: the regular expression engine. Data type: string. This parameter is optional.
    -   i: specifies that this function is not case-sensitive.
-   Response parameters

    If the string matches the regular expression, `true` is returned. Otherwise, `false` is returned.

-   Examples

    ```
    url = concat('http://', $host, $uri)
    m1 = match_re(url, 'http://. *\.dslex\.com/.*')
    m2 = match_re(url, '^http://. *\.alibaba\.com\.cn/. *\.d\\.html(\?. *)? $')
    m3 = match_re(url, '^http://. *.test.dslex.com/. *\.d\.html(\?. *)? $')
    m4 = match_re(url, '^http://. *\.alibaba\.com\.cn/zt_d/')
    m5 = match_re(url, '^http://tech.alibaba.com.cn/zt_d/we2015/?$')
    m6 = match_re($args, 'from=wap1$')
    m7 = match_re($args, 'from=comos1$')
    
    if and(m1, or(m2, m3), not(m4), not(m5), or(not(m6), not(m7))) {                                                                                                                                       
        add_rsp_header('USER-DEFINED-1', 'hit1')                                                                                                                                                           
        add_rsp_header('USER-DEFINED-2', 'hit2')                                                                                                                                                         
    ```


## capture\_re

Details about this function:

-   Syntax: `capture_re(s, p [,init])`.
-   Description

    Captures the matches of a string and returns the matching substrings. The PCRE engine is used.

-   Parameters
    -   s: the string that you want to match. Data type: string.
    -   p: the regular expression for matching. Data type: string.
    -   init: the position to start matching, counting from 1. Data type: integer.
-   Response parameters

    Returns the matching substrings in the dictionary type if the string matches the regular expression. Otherwise, an empty dictionary is returned.

-   Examples

    ```
    pcs = capture_re($request_uri,'^/([^/]+)/([^/]+)([^?] +)\?(.*)')
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
    ```


## gsub\_re

Details about this function:

-   Syntax: `gsub_re(subject, regex, replace [,option])`.
-   Description

    Replaces all matches of a string and returns the string after the replacement. The PCRE engine is used.

-   Parameters
    -   subject: the string that you want to match. Data type: string.
    -   regex: the regular expression. Data type: string.
    -   replace: the string for replacement. Data type: string.

        You can specify the `replace` parameter by using the matching substrings.

        -   $0: specifies all substrings that match `regex`.
        -   $N: specifies the substring that matches the Nth parenthesized subexpression `()` of `regex`.
    -   option: the regular expression engine. Data type: string. This parameter is optional.
-   Response parameters

    Replaces all substrings that match the specified `regex` parameter in the specified `subject` parameter with those specified by the `replace` parameter and returns the string after the replacement.

-   Examples

    ```
    //Output:
    //X-DEBUG-GSUB-RE: [Hello,H], [Es,E]
    
    subject = 'Hello, Es'
    regex = '([a-zA-Z])[a-z]+'
    replace = '[$0,$1]'
    add_rsp_header('X-DEBUG-GSUB-RE', gsub_re(subject, regex, replace))                                                                                                                                               
    ```

-   References

    For more information about PCRE, see [pcre2syntax man page](https://www.pcre.org/current/doc/html/pcre2syntax.html).


## split

Details about this function:

-   Syntax: `split(s [,sep])`.
-   Description

    Splits a string into an array of substrings and returns the array.

-   Parameters
    -   s: the string that you want to split. Data type: string.
    -   sep: the separator that is used to split the string. Data type: string.
-   Response parameters

    Returns an array of key-value pairs in the dictionary type. The value of the `key` parameter is a number that starts from 1, for example, \[1\]=xx and \[2\]=y. If `sep` is left empty, the string is split by whitespace characters. Whitespace characters include space characters and tab characters \(\\t\).

-   Examples

    ```
    //Request: ? from=xx1,xx2,xx3  
    //Response: [1]=xx1  
    //[2]=xx1
    
    if $arg_from {
        t = split($arg_from, ',')
        if get(t, 1) {
            say(concat('[1]=', get(t, 1)))
        }
        if get(t, 2) {
            say(concat('[2]=', get(t, 1)))
        }
    }                                                                                                                                            
    ```


## split\_as\_key

Details about this function:

-   Syntax: `split_as_key(s [,sep])`.
-   Description

    Splits a string into an array of substrings and returns the array.

-   Parameters
    -   s: the string that you want to split. Data type: string.
    -   sep: the separator that is used to split the string. Data type: string.
-   Response parameters

    Returns response parameters in the same way as the `split()` function. However, the `key` parameter is named after each split element: `Element 1` -\> `Element 2`.

-   Examples

    ```
    //Request: ? from=xx1,xx2,xx3  
    //Response: xx2=xx2 u=hi,dsl
    //xx1=xx1 u=hi,dsl
    //xx3=xx3 u=hi,dsl     
    
    def echo_each(k, v, u) {
        s = concat(k, '=', v, ' u=', get(u, 1))
        say(s) 
    }
    if $arg_from {
        t = split_as_key($arg_from, ',')
        foreach(t, echo_each, ['hi,dsl'])
    }                                                                                                                                     
    ```


## tohex

Details about this function:

-   Syntax: `tohex(s)`.
-   Description

    Converts a string to a hexadecimal string.

-   Parameters

    s: the string that you want to convert.

-   Response parameters

    Returns the hexadecimal string that is converted from the string specified by the `s` parameter.

-   Examples

    ```
    //A response header is added.
    //X-DSL-TOHEX: 4ad583af22c2e7d40c1c916b2920299155a46464     
    
    digest = sha1('xxxx')
    add_rsp_header('X-DSL-TOHEX', tohex(digest))                                                                                                                                        
    ```


## tostring

Details about this function:

-   Syntax: `tostring(a)`.
-   Description

    Converts data of any type to a string.

-   Parameters

    a: the data that you want to convert. Data type: any type.

-   Response parameters

    Returns the string that is converted from the value specified by the `a` parameter.

-   Examples

    ```
    //A response header is added.
    //X-DSL-TOSTRING: 123    
    
    s = tostring(123)
    add_rsp_header('X-DSL-TOSTRING', s)                                                                                                                              
    ```


## tochar

Details about this function:

-   Syntax: `tochar(n1, n2, ...)`.
-   Description
    -   Converts one or more internal integers \(ASCII values\) to a string. For example, 48 corresponds to the character "0".
    -   The length of the returned string is based on the number of specified parameters.
-   Parameters

    nX: the integers that you want to convert. You can specify multiple integers.

-   Response parameters

    Returns a string converted from integers.

-   Examples

    ```
    //Output: A response header is added.
    //X-DSL-TOCHAR: a
    //X-DSL-TOCHAR: ab
    
    add_rsp_header('X-DSL-TOCHAR', tochar(97))
    add_rsp_header('X-DSL-TOCHAR', tochar(97, 98), true)
    
    //Output: A response header is added.
    //Content-Disposition: attachment;filename="The value of the filename parameter"   
    
    if $arg_filename {
        hn = 'Content-Disposition'
        add_rsp_header('Content-Disposition', concat('attachment;filename=', tochar(34), filename, tochar(34)))
        add_rsp_header(hn, hv)
    }                                                                                                                                      
    ```


