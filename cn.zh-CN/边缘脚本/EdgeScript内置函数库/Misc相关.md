# Misc相关 {#concept_1322989 .concept}

本文为您介绍Misc相关函数的语法、说明、参数、返回值和示例。

## base64\_enc {#section_xrm_qws_dhv .section}

函数详细解释如下：

-   语法：`base64_enc(s [, no_padding])`。
-   说明

    base64编码。

-   参数
    -   s：待编码的字符串。
    -   no\_padding：`true`表示无填充，默认`false`。
-   返回值

    base64编码后的字符串。

-   示例

    ``` {#codeblock_ivw_wv0_45q}
    if $http_data {
       decdata = base64_dec($http_data)
       say(concat('base64_decdata=', decdata))
       say(concat('base64_encdata=', base64_enc('hello, dsl'))) 
    }
    
    请求header: "data: aGVsbG8sIGRzbA=="
    响应：base64_decdata=hello, dsl
    base64_encdata=aGVsbG8sIGRzbA==
    ```


## base64\_dec {#section_afr_4ol_cu9 .section}

函数详细解释如下：

-   语法：`base64_dec(s)`。
-   说明

    base64编码。

-   参数

    s：待编码的字符串。

-   返回值

    base64编码后的字符串。

-   示例

    ``` {#codeblock_6m4_idk_eb3}
    if $http_data {
       decdata = base64_dec($http_data)
       say(concat('base64_decdata=', decdata))
       say(concat('base64_encdata=', base64_enc('hello, dsl'))) 
    }
    
    请求header: "data: aGVsbG8sIGRzbA=="
    响应：base64_decdata=hello, dsl
    base64_encdata=aGVsbG8sIGRzbA==
    ```


## url\_escape {#section_l9q_hn2_m1b .section}

函数详细解释如下：

-   语法：`url_escape(s)`。
-   说明

    URL编码。

-   参数：

    s：待编码的字符串。

-   返回值

    URL编码后的字符串。

-   示例

    ``` {#codeblock_cde_nev_hgn}
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
    ```


## url\_unescape {#section_ph0_rha_htm .section}

函数详细解释如下：

-   语法：`url_unescape(s)`。
-   说明：

    URL编码。

-   参数：

    s：待编码的字符串。

-   返回值：

    URL编码后的字符串。

-   示例

    ``` {#codeblock_0s3_ebf_fsr}
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
    ```


## rand {#section_2mj_x6g_ay3 .section}

函数详细解释如下：

-   语法：`rand(n1, n2)`。
-   说明

    生成随机数，随机数范围：n1 <= 返回值 <= n2。

-   参数
    -   n1：随机数下限。
    -   n2：随机数上限。
-   返回值

    返回生成的随机数。

-   示例

    ``` {#codeblock_aj6_z5x_6tg}
    r = rand(1,100)
    ```


## rand\_hit {#section_gv8_0p3_p7g .section}

函数详细解释如下：

-   语法：`rand_hit(ratio)`。
-   说明

    按指定概率返回真假。

-   参数

    ratio：为真概率，有效值范围为\[0-100\]。

-   返回值

    按ratio概率返回`true`。例如：当ratio为100时，返回`true`，当ratio为0时，返回`false`。

-   示例

    ``` {#codeblock_n0o_3e6_ecr}
    rand_hit(80)
    ```


## crc {#section_n3v_mkk_rkb .section}

函数详细解释如下：

-   语法：`crc(s)`。
-   说明

    计算crc摘要。

-   参数

    s：待计算摘要的字符串。

-   返回值

    返回`s`的crc摘要。

-   示例

    ``` {#codeblock_k19_cmc_914}
    crc('hello edgescript')
    ```


## tonumber {#section_emy_zhf_iw3 .section}

函数详细解释如下：

-   语法：`tonumber(s [, base])`。
-   说明

    类型转换，将字符串类型转换为数字类型。

-   参数
    -   s：待转换的字符串。
    -   base：可指定目标转换进制，可用值：10和16，默认10进制。
-   示例

    ``` {#codeblock_faj_28b_izt}
    n = tonumber('100')
    say(concat('tonumber()=', n))
    
    输出：tonumber()=100
    ```


