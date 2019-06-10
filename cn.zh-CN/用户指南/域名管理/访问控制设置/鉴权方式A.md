# 鉴权方式A {#concept_oxj_wrm_j2b .concept}

本文为您介绍了鉴权方式A的原理并用示例说明。鉴权功能主要用于保护用户站点的内容资源不被非法站点下载盗用。

## 原理说明 {#section_rzx_ttm_j2b .section}

访问加密URL构成：

``` {#codeblock_c0h_r5h_eax}
http://DomainName/Filename?auth_key=timestamp-rand-uid-md5hash
```

鉴权字段描述

|字段|描述|
|:-|:-|
|DomainName|CDN站点的域名。|
|timestamp|失效时间，整形正数，固定长度10，值为1970年1月1日以来的当前时间秒数+过期时间秒数。用来控制失效时间，过期时间由客户端设置，若设置为1800s，您访问CDN的时间超过1800s后，该鉴权失效。 例如您设置访问时间为2020-08-15 15:00:00，则链接的真正失效时间为2020-08-15 15:30:00。

 |
|rand|随机数。建议使用UUID，不能包含中划线`-`，例如：477b3bbc253f467b8def6711128c7bec。|
|uid|用户ID，暂未使用（设置成0即可\)。|
|md5hash|通过md5算法计算出的验证串，由数字0-9和小写英文字母a-z混合组成，固定长度32。|
|PrivateKey|您设定的鉴权密钥。|
|Filename|实际回源访问的URL，鉴权时Filename需以`/`开头。|

CDN服务器接收请求后，会首先判断请求中的`timestamp`是否小于当前时间。

-   如果小于当前时间，服务器判定过期失效并返回HTTP 403错误。
-   如果大于当前时间，构造出一个同样的字符串，参考下方`sstring`字符串，然后使用MD5算法算出`HashValue`，再和请求中`md5hash`进行比对。
    -   结果一致，鉴权通过，返回文件。
    -   结果不一致，鉴权失败，返回HTTP 403错误。

`HashValue`是通过以下字符串计算出来的：

``` {#codeblock_o3m_kdk_k57}
sstring = "URI-Timestamp-rand-uid-PrivateKey"（URI是用户的请求对象相对地址，不包含参数，如/Filename）
HashValue = md5sum(sstring)
```

## 示例说明 {#section_a1y_ttm_j2b .section}

您可以通过以下示例说明更好地理解鉴权方式A的实现。

1.  通过`req_auth`请求对象。

    ``` {#codeblock_8df_8sj_iv1}
    http:// cdn.example.com/video/standard/1K.html
    ```

2.  设置密钥为：aliyuncdnexp1234（您可以自行配置）。
3.  设置鉴权配置文件有效时间为：2015年10月10日00:00:00，计算出秒数为1444435200。
4.  CDN服务器会构造一个用于计算Hashvalue的签名字符串。

    ``` {#codeblock_6ja_t1q_9hl}
    /video/standard/1K.html-1444435200-0-0-aliyuncdnexp1234
    ```

5.  根据该签名字符串，CDN服务器会计算出HashValue。

    ``` {#codeblock_7cp_e91_qys}
    HashValue = md5sum("/video/standard/1K.html-1444435200-0-0-aliyuncdnexp1234") = 80cd3862d699b7118eed99103f2a3a4f
    ```

6.  请求时url为：

    ``` {#codeblock_x42_42v_a9w}
    http://cdn.example.com/video/standard/1K.html?auth_key=1444435200-0-0-80cd3862d699b7118eed99103f2a3a4f
    ```

    如果计算出的HashValue与您请求中带的md5hash=80cd3862d699b7118eed99103f2a3a4f值一致，则鉴权通过。


鉴权方式B和鉴权方式C具体原理和示例，请参见[鉴权方式B](intl.zh-CN/用户指南/域名管理/访问控制设置/鉴权方式B.md#)、[鉴权方式C](intl.zh-CN/用户指南/域名管理/访问控制设置/鉴权方式C.md#)。

