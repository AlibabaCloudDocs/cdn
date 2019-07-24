# JSON相关 {#concept_1322988 .concept}

本文为您介绍了JSON相关的函数。

## json\_enc {#section_c5a_j1r_f8q .section}

函数说明如下所示。

-   语法：`json_enc(d)`。
-   说明：JSON编码。
-   参数：

    d：待编码的字典对象

-   返回值：成功返回编码后的字符串，失败返回false。
-   示例如下所示。

    ``` {#codeblock_4sq_tgt_x5b}
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
    ```


## json\_dec {#section_kk1_zv2_ly2 .section}

函数说明如下所示。

-   语法：`json_dec(s)`。
-   说明：JSON解码。
-   参数：

    s：待解码的json格式字符串

-   返回值：成功返回解码后的字典，失败返回false。
-   示例如下所示。

    ``` {#codeblock_cyj_76o_m4j}
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
    ```


