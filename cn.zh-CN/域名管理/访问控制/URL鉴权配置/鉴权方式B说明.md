---
keyword: [阿里云cdn鉴权, cdn鉴权]
---

# 鉴权方式B说明

URL鉴权功能主要用于保护用户站点资源不被非法站点下载盗用。阿里云CDN为您提供了三种鉴权方式，本文为您详细介绍鉴权方式B的原理和示例说明。

## 原理说明

访问加密URL格式：

```
http://DomainName/timestamp/md5hash/FileName
```

当鉴权通过时，实际回源的URL格式：

```
http://DomainName/FileName
```

鉴权字段描述如下表所示。

|字段|描述|
|:-|:-|
|DomainName|CDN站点的域名。|
|timestamp|资源失效时间，作为URL的一部分，同时作为计算`md5hash`的一个因子，格式为： YYYYMMDDHHMM，有效时间1800s。 例如您设置访问时间为2020-08-15 15:00:00，则链接的真正失效时间为2020-08-15 15:30:00。 |
|md5hash|通过md5算法计算出的验证串，由数字0-9和小写英文字母a-z混合组成，固定长度32。|
|Filename|实际回源访问的URL，鉴权时Filename需以`/`开头。|

## 示例说明

通过以下示例说明，您可以准确理解鉴权方式B的实现方式。

1.  回源请求对象。

    ```
    http://cdn.example.com/4/44/44c0909bcfc20a01afaf256ca99a8b8b.mp3
    ```

2.  密钥为：aliyuncdnexp1234。
3.  访问源服务器时间为： 201508150800。
4.  CDN服务器构造一个用于计算`Hashvalue`的签名字符串。

    ```
    aliyuncdnexp1234201508150800/4/44/44c0909bcfc20a01afaf256ca99a8b8b.mp3
    ```

5.  服务器根据签名字符串`Hashvalue`计算`md5hash`。

    ```
    md5hash = md5sum("aliyuncdnexp1234201508150800/4/44/44c0909bcfc20a01afaf256ca99a8b8b.mp3") = 9044548ef1527deadafa49a890a377f0
    ```

6.  加密URL请求。

    **说明：** 如果您加密URL中有中文汉字，请先对其进行URL转码（即encode），然后执行该步骤。

    ```
    http://cdn.example.com/201508150800/9044548ef1527deadafa49a890a377f0/4/44/44c0909bcfc20a01afaf256ca99a8b8b.mp3
    ```


如果计算出来的`md5hash`值与请求中带的`md5hash`值相同，都为9044548ef1527deadafa49a890a377f0，则鉴权通过；反之鉴权失败。

