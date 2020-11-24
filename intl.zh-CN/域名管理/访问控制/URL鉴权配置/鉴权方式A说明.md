---
keyword: [阿里云cdn鉴权, cdn鉴权]
---

# 鉴权方式A说明

URL鉴权功能主要用于保护用户站点资源不被非法站点下载盗用。阿里云CDN为您提供了三种鉴权方式，本文为您详细介绍鉴权方式A的原理和示例说明。

## 原理说明

访问加密URL构成：

```
http://DomainName/Filename?auth_key=timestamp-rand-uid-md5hash
```

鉴权字段描述如下表所示。

|字段|描述|
|:-|:-|
|DomainName|CDN站点的域名。|
|Filename|实际回源访问的URL，鉴权时Filename需以正斜线（`/`）开头。|
|auth\_key|您设定的鉴权密钥。|
|timestamp|失效时间，整型正数，固定长度10，值为1970年1月1日以来的当前时间秒数+过期时间秒数。用来控制失效时间，过期时间由客户端设置，若设置为1800s，您访问CDN的时间超过1800s后，该鉴权失效。 例如，您设置访问时间为2020-08-15 15:00:00，则链接的真正失效时间为2020-08-15 15:30:00。 |
|rand|随机数。建议使用UUID，不能包含中划线（`-`），例如：477b3bbc253f467b8def6711128c7bec。|
|uid|用户ID，暂未使用（设置成0即可）。|
|md5hash|通过md5算法计算出的字符串，由数字0-9和小写英文字母a-z混合组成，固定长度32。|

CDN服务器接到资源访问请求后，判断最终生成鉴权URL请求中的`timestamp`+`鉴权key的有效时间`是否小于当前时间。

-   如果`timestamp`+`鉴权key的有效时间`小于当前时间，服务器判定过期失效，并返回HTTP 403错误。
-   如果`timestamp`+`鉴权key的有效时间`大于当前时间，构造出一个同样的字符串，参考下方`sstring`字符串，然后使用MD5算法算出`HashValue`的值，再与请求中`md5hash`的值进行比对。

    -   结果一致，鉴权通过，返回资源请求。
    -   结果不一致，鉴权失败，返回HTTP 403错误。
    `HashValue`的值是通过以下字符串计算得到的。

    ```
    sstring = "URI-Timestamp-rand-uid-PrivateKey"（URI是用户的请求对象相对地址，不包含参数，如/Filename）
    HashValue = md5sum(sstring)
    ```


## 示例说明

通过以下示例说明，您可以准确理解鉴权方式A的实现方式。

1.  通过`req_auth`请求对象。

    ```
    http:// cdn.example.com/video/standard/1K.html
    ```

2.  设置密钥为：aliyuncdnexp1234。
3.  设置鉴权配置文件有效时间为：2015年10月10日00:00:00，计算出秒数为：1444435200。
4.  CDN服务器会构造一个用于计算`Hashvalue`的签名字符串。

    ```
    /video/standard/1K.html-1444435200-0-0-aliyuncdnexp1234
    ```

5.  根据该签名字符串，CDN服务器会计算出`Hashvalue`。

    ```
    HashValue = md5sum("/video/standard/1K.html-1444435200-0-0-aliyuncdnexp1234") = 80cd3862d699b7118eed99103f2a3a4f
    ```

6.  加密URL请求。

    ```
    http://cdn.example.com/video/standard/1K.html?auth_key=1444435200-0-0-80cd3862d699b7118eed99103f2a3a4f
    ```


如果计算出来的`HashValue`值与请求中带的`md5hash`值相同，都为80cd3862d699b7118eed99103f2a3a4f，则鉴权通过；反之鉴权失败。

