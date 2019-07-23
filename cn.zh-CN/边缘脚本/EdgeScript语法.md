# EdgeScript语法 {#concept_1322634 .concept}

介绍EdgeScript的语法。

## 注释 {#section_zu3_zeg_yz7 .section}

以\#开头的当前行后续内容，均为注释。

例如：\# this is annotation

## 标识符规则 {#section_c6e_xdw_qw8 .section}

标识符规则如下：

-   由字母、数字、下划线组成，数字不能开头，区分大小写。
-   变量名（内置 、自定义）和函数名（内置 、自定义）均遵守标识符规则。

## 数据类型 {#section_02i_sow_xos .section}

数据类型规则如下：

-   字符串

    字面常量：使用单引号 '' 括起，例如：'hello, EdgeScript'

-   数字

    字面常量：十进制数字，例如：10、-99、1.1

-   布尔值

    字面常量：true、false

-   字典

    字面常量：

    -   \[\] : 空
    -   \['key1', 'key2', 100\] ：
        -   1 -\> 'key1'
        -   2 -\> 'key2'
        -   3 -\> 'key3'
    -   \['key1' = 'value1', 'key2' = 1000\]
        -   'key1' -\> 'value1'
        -   'key2' -\> 1000

## 变量 {#section_4hc_mgx_nru .section}

变量规则如下：

-   定义

    赋值即定义

-   使用
    -   内置和自定义变量，均由变量名进行引用
        -   引用内置变量：host
        -   引用自定义变量：seckey
    -   为强调变量的内置属性，可通过$进行引用

        引用内置变量：$host

    -   自定义变量的名称不能与内置变量同名。
    -   内置变量，请参考[EdgeScript内置变量表](cn.zh-CN/边缘脚本/EdgeScript内置变量表.md#)。

## 运算符 {#section_ky3_6gi_lm3 .section}

运算符规则如下：

-   = ：赋值运算符
    -   举例：seckey = 'ASDLFJ234dxvf34sDF'
    -   举例：seckeys = \['key1', 'key2'\]
-   - ：负号运算符

    举例：inum = -10

-   对各数据类型的操作，不再另行支持运算符，均由内置函数支持，请参见[条件判断相关](cn.zh-CN/边缘脚本/EdgeScript内置函数库/条件判断相关.md#)。
    -   各数据类型内置函数支持
        -   字符串类型内置处理函数
        -   数字类型内置处理函数
        -   字典类型内置处理函数
    -   例子
        -   例如：sval = concat\(sval, 'trail'\)
        -   例如：len\(arrvar\)

## 语句 {#section_0hc_ppl_bcv .section}

语句规则如下：

-   条件判断
-   condition可由如下语法元素组成
    -   字面值
    -   变量
    -   函数调用
-   body部分
    -   允许空body
    -   允许多语句：一行一条语句
-   支持多层嵌套
-   CodingStyle

    语法强制要求左大扩号跟随在if condition之后，同行。


## 函数 {#section_m5n_3iq_tc2 .section}

函数语法和定义说明如下：

-   定义语法

    ``` {#codeblock_lbt_5lq_qqk .language-java}
    def 函数名(参数列表) {
       ...
    }
    ```

-   定义说明
    -   形参列表
        -   允许无参
        -   允许多参：由逗号分隔
    -   函数体部分
        -   允许空body
        -   允许多语句：一行一条语句
        -   返回值：支持return语句
    -   CodingStyle

        语法强制要求左大扩号跟随在 def 函数名\(参数列表\) 之后，同行。

-   函数调用

    无论内置、自定义函数，均通过 函数名\(\) 进行调用。


## 其他 {#section_soe_qz5_ef5 .section}

EdgeScript全文不允许出现任何双引号。

