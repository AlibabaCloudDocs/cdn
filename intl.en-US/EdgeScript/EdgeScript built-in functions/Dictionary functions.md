# Dictionary functions

This topic describes the syntax, description, parameters, and response parameters of dictionary functions. This topic also provides examples of these functions.

## set

Sets key-value pairs in a dictionary specified by the d parameter. The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|set\(d, k, v\)|
|Parameters|-   d: the name of the dictionary.
-   k: the key. Data type: any type.
-   v: the value. Data type: any type. |
|Examples|-   Example 1

    ```
outer_keys=['e66fd4aa-f281-472f-b919-fc7e7474de25', '66fee78d-1887-42ec-9119-a9b50b7fbca2']
say(concat('keys[1]=', get(outer_keys, 1)))
say(concat('keys[2]=', get(outer_keys, 2)))

inner_keys=[]
set(inner_keys, 'dev', '243390eb-00b7-4551-a6b8-021bb34d1674')
set(inner_keys, 'zeus', '4747d33b-12b0-45e6-ac10-a8e191d6adaa')

def echo_each(k, v, u) {
    s = concat('keys[', k, ']=', v)
    say(s)
}
foreach(inner_keys, echo_each, [])                                                                                                                                             
    ```

-   Example 2

    ```
d_inner = []
set(d_inner, 'name', 'inner dsl')

d_outer = []
set(d_outer, 'dictA', d_inner)

v = get(d_outer, 'dictA')
if v {
    v = get(v, 'name')
    if v {
        add_rsp_header('X-DSL-NESTED-DICT', v)
    }
}
    ``` |
|Response parameters|Returns a value of true. Response parameters of Example 1 and Example 2:-   Example 1

    ```
keys[1]=e66fd4aa-f281-472f-b919-fc7e7474de25
keys[2]=66fee78d-1887-42ec-9119-a9b50b7fbca2
keys[dev]=243390eb-00b7-4551-a6b8-021bb34d1674
keys[zeus]=4747d33b-12b0-45e6-ac10-a8e191d6adaa
    ```

-   Example 2: A response header is added.

    ```
X-DSL-NESTED-DICT: inner dsl
    ``` |

## get

Retrieves the value \(v\) that corresponds to a key \(k\) from a dictionary \(d\). The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|get\(d, k\)|
|Parameters|-   d: the name of the dictionary.
-   k: the key. Data type: any type. |
|Examples|```
outer_keys=['e66fd4aa-f281-472f-b919-fc7e7474de25', '66fee78d-1887-42ec-9119-a9b50b7fbca2']
say(concat('keys[1]=', get(outer_keys, 1)))
say(concat('keys[2]=', get(outer_keys, 2)))

inner_keys=[]
set(inner_keys, 'dev', '243390eb-00b7-4551-a6b8-021bb34d1674')
set(inner_keys, 'zeus', '4747d33b-12b0-45e6-ac10-a8e191d6adaa')

def echo_each(k, v, u) {
    s = concat('keys[', k, ']=', v)
    say(s)
}
foreach(inner_keys, echo_each, [])                                                                                                                                             
``` |
|Response parameters|If the function succeeds, the value that corresponds to the specified key is returned. Otherwise, a value of false is returned. Response parameters of this example:```
keys[1]=e66fd4aa-f281-472f-b919-fc7e7474de25
keys[2]=66fee78d-1887-42ec-9119-a9b50b7fbca2
keys[dev]=243390eb-00b7-4551-a6b8-021bb34d1674
keys[zeus]=4747d33b-12b0-45e6-ac10-a8e191d6adaa
``` |

## foreach

Details about this function:

-   Traverses elements in a dictionary \(d\) and calls a callback function \(f\) for each element.
-   Specify the f parameter in the syntax of `f(key, value, user_data)`.
-   When the `f()` function returns false, the `foreach()` loop ends.

The following table describes the details about this function:

|Item|Description|
|----|-----------|
|Syntax|foreach\(d, f, user\_data\)|
|Parameters|-   d: the name of the dictionary.
-   f: the callback function.
-   user\_data: the user data that you want to transmit. Data type: dictionary. |
|Examples|-   Example 1

    ```
outer_keys=['e66fd4aa-f281-472f-b919-fc7e7474de25', '66fee78d-1887-42ec-9119-a9b50b7fbca2']
say(concat('keys[1]=', get(outer_keys, 1)))
say(concat('keys[2]=', get(outer_keys, 2)))

inner_keys=[]
set(inner_keys, 'dev', '243390eb-00b7-4551-a6b8-021bb34d1674')
set(inner_keys, 'zeus', '4747d33b-12b0-45e6-ac10-a8e191d6adaa')

def echo_each(k, v, u) {
    s = concat('keys[', k, ']=', v)
    say(s)
}
foreach(inner_keys, echo_each, [])                                                                                                                                             
    ```

-   Example 2

Prints the first two `M3U8` slices and ends the foreach loop.

    ```
def echo_each(k, v, u) {
    say(v)

    if match_re(v, '.*ts') {
        ts_cnt = get(u, 'ts_cnt')
        ts_cnt = add(ts_cnt, 1)
        set(u, 'ts_cnt', ts_cnt)

        if ge(ts_cnt, 2) {
            return false
        }
    }
}

m3u8 = ''
m3u8 = concat(m3u8, '#EXTM3U8', '\n')
m3u8 = concat(m3u8, '#EXT-X-MEDIA-SEQUENCE:140651513\n')
m3u8 = concat(m3u8, '#EXT-X-TARGETDURATION:10\n')
m3u8 = concat(m3u8, '#EXTINF:8,\n')
m3u8 = concat(m3u8, 'http://vapp1.fw.live.cntv.cn/cache/289_/seg0/index140651514_140651513.ts\n')
m3u8 = concat(m3u8, '#EXTINF:9,\n')
m3u8 = concat(m3u8, 'http://vapp1.fw.live.cntv.cn/cache/289_/seg0/index140651514_140651514.ts\n')
m3u8 = concat(m3u8, '#EXTINF:10,\n')
m3u8 = concat(m3u8, 'http://vapp1.fw.live.cntv.cn/cache/289_/seg0/index140651514_140651515.ts\n')

lines = split(m3u8, '\n')
u = []
set(u, 'ts_cnt', 0)
foreach(lines, echo_each, u)
    ``` |
|Response parameters|Returns a value of true. Response parameters of Example 1 and Example 2:-   Example 1

    ```
keys[1]=e66fd4aa-f281-472f-b919-fc7e7474de25
keys[2]=66fee78d-1887-42ec-9119-a9b50b7fbca2
keys[dev]=243390eb-00b7-4551-a6b8-021bb34d1674
keys[zeus]=4747d33b-12b0-45e6-ac10-a8e191d6adaa
    ```

-   Example 2

    ```
#EXTM3U8
#EXT-X-MEDIA-SEQUENCE:140651513
#EXT-X-TARGETDURATION:10
#EXTINF:8,
http://vapp1.fw.live.cntv.cn/cache/289_/seg0/index140651514_140651513.ts
#EXTINF:9,
http://vapp1.fw.live.cntv.cn/cache/289_/seg0/index140651514_140651514.ts
    ``` |

## del

Deletes key-value pairs from a dictionary \(d\). The following tables describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|del\(d, k\)|
|Parameters|-   d: the name of the dictionary.
-   k: the key. Data type: any type. |
|Examples|```
var_a = []
set(var_a, 'note_a', 'note a info')
if get(var_a, 'note_a') {
    add_rsp_header('X-RESPOND-OUTPUT', 'found var_a key', true)
} else {
    add_rsp_header('X-RESPOND-OUTPUT', 'del var_a key', true)
}
del(var_a, 'note_a')
if get(var_a, 'note_a') {
    add_rsp_header('X-RESPOND-OUTPUT', 'found var_a key', true)
} else {
    add_rsp_header('X-RESPOND-OUTPUT', 'del var_a key', true)
}
``` |
|Response parameters|Returns a value of true. Response parameter for this example:```
X-RESPOND-OUTPUT: found var_a key
X-RESPOND-OUTPUT: del var_a key
``` |

