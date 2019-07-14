# 鉴权方式B {#concept_k5t_zrm_j2b .concept}

阿里云CDN鉴权功能为您提供了三种方式，本文档为您介绍了鉴权方式B的原理并用示例说明。鉴权功能主要用于保护用户站点的内容资源不被非法站点下载盗用。

## 原理说明 {#section_8r6_d7i_kil .section}

访问加密URL格式：

``` {#codeblock_zoh_abm_l1g}
http://DomainName/timestamp/md5hash/FileName
```

当鉴权通过时，实际回源的URL是：

``` {#codeblock_10l_l1p_k3j}
http://DomainName/FileName
```

鉴权字段描述

|字段|描述|
|:-|:-|
|DomainName|CDN站点的域名。|
|timestamp|资源失效时间，作为URL的一部分，同时作为计算`md5hash`的一个因子，格式为： YYYYMMDDHHMM，有效时间1800s。 例如您设置访问时间为2020-08-15 15:00:00，则链接的真正失效时间为2020-08-15 15:30:00。

 |
|md5hash|通过md5算法计算出的验证串，由数字0-9和小写英文字母a-z混合组成，固定长度32。|
|PrivateKey|您设定的鉴权密钥。|
|Filename|实际回源访问的URL，鉴权时Filename需以`/`开头。|

## 示例说明 {#section_ycm_uzd_hif .section}

您可以通过以下示例说明更好地理解鉴权方式B的实现。

1.  回源请求对象：

    ``` {#codeblock_m22_mca_1od}
    http://cdn.example.com/4/44/44c0909bcfc20a01afaf256ca99a8b8b.mp3
    ```

2.  密钥设为：aliyuncdnexp1234 \(您自行设置\)。
3.  访问源服务器时间为 201508150800（格式为： YYYYMMDDHHMM）。
4.  CDN服务器会构造一个用于计算`Hashvalue`的签名字符串。

    ``` {#codeblock_e76_t8w_0un}
    aliyuncdnexp1234201508150800/4/44/44c0909bcfc20a01afaf256ca99a8b8b.mp3
    ```

5.  服务器根据该签名字符串计算`md5hash`。

    ``` {#codeblock_q65_44q_2qr}
    md5hash = md5sum("aliyuncdnexp1234201508150800/4/44/44c0909bcfc20a01afaf256ca99a8b8b.mp3") = 9044548ef1527deadafa49a890a377f0
    ```

6.  请求url为：

    ``` {#codeblock_gda_vao_bhe}
    http://cdn.example.com/201508150800/9044548ef1527deadafa49a890a377f0/4/44/44c0909bcfc20a01afaf256ca99a8b8b.mp3
    ```

    如果计算出来的`md5hash`与您请求中带的`md5hash`值（9044548ef1527deadafa49a890a377f0 ）一致，鉴权通过。


鉴权方式A和鉴权方式C具体原理和示例，请参见[鉴权方式A](intl.zh-CN/域名管理/配置访问控制/配置URL鉴权/配置鉴权方式A.md#)、[鉴权方式C](intl.zh-CN/域名管理/配置访问控制/配置URL鉴权/鉴权方式C.md#)。

