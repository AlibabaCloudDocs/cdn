# 鉴权方式C {#concept_fvc_bsm_j2b .concept}

本文为您介绍了鉴权方式C的原理并用示例说明。

## 原理说明 { .section}

访问加密URL格式有如下两种格式。

-   格式1

    ``` {#codeblock_lyf_u4i_240}
    http://DomainName/{<md5hash>/<timestamp>}/FileName
    ```

-   格式2

    ``` {#codeblock_965_h7m_zz1}
    http://DomainName/FileName{&KEY1=<md5hash>&KEY2=<timestamp>}
    ```


**说明：** `{}`中的内容表示在标准URL基础上添加的加密信息。

鉴权字段描述

|字段|描述|
|:-|:-|
|PrivateKey|您设定的鉴权密钥。|
|FileName|实际回源访问的URL，鉴权时Filename需以`/`开头。|
|timestamp|访问源服务器时间，取UNIX时间。未加密的字符串，以明文表示。固定长度10，1970年1月1日以来的秒数，表示为十六进制。|
|DomainName|CDN站点的域名。|

## 示例说明 {#section_52z_jt5_nne .section}

-   PrivateKey取值：`aliyuncdnexp1234`。
-   FileName取值：`/test.flv`。
-   timestamp取值：`55CE8100`。
-   md5hash计算值为：

    ``` {#codeblock_5j9_e5e_y4m}
    md5hash = md5sum(aliyuncdnexp1234/test.flv55CE8100) = a37fa50a5fb8f71214b1e7c95ec7a1bd
    ```

-   生成加密URL:
    -   格式一：

        ``` {#codeblock_1d1_sfd_tsk}
        http://cdn.example.com/a37fa50a5fb8f71214b1e7c95ec7a1bd/55CE8100/test.flv
        ```

    -   格式二：

        ``` {#codeblock_avs_r5z_akv}
        http://cdn.example.com/test.flv?KEY1=a37fa50a5fb8f71214b1e7c95ec7a1bd&KEY2=55CE8100
        ```


当您使用加密URL访问加速节点，CDN服务器先把加密串1提取出来，并得到原始的URL的`FileName`和访问时间，然后按照定义的业务逻辑进行验证，验证步骤如下：

1.  使用原始的URL中的Filename、请求时间及PrivateKey进行md5加密得到一个加密串2。
2.  比较加密串2与加密串1是否一致，如果不一致则拒绝。
3.  取加速节点服务器当前时间，并与从访问URL中所带的明文时间相减，判断是否超过设置的时限t\(时间域值t默认为1800s\)。

    -   时间差小于设置时限，视作合法请求，CDN加速节点正常响应。
    -   时间差大于设置时限，拒绝该请求并返回HTTP 403。
    **说明：** 有效时间1800s是指，当您访问源服务器时间超过自定义时间的1800s后，该鉴权失效。例如您设置了访问时间2020-08-15 15:00:00，链接真正失效时间是2020-08-15 15:30:00。


