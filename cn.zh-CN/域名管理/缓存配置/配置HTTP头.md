---
keyword: [HTTP响应头, CDN, 跨域请求]
---

# 配置HTTP头

HTTP消息头准确描述了正在获取的资源、服务器或客户端的行为，定义了HTTP事务中的具体操作参数。通过本文档，您可以了解设置HTTP头响应的操作方法。

HTTP消息头是指，在超文本传输协议HTTP（Hypertext Transfer Protocol）的请求和响应消息中，协议头部的组件。

在HTTP消息头中，按其出现的上下文环境，分为通用头、请求头、响应头等。

**说明：**

-   HTTP响应头的设置会影响该加速域名下所有资源，当您通过客户端（例如浏览器）访问资源时，会影响请求响应，但不会影响缓存服务器。
-   目前不支持泛域名设置。

1.  登录[CDN控制台](https://cdn.console.aliyun.com)。

2.  在左侧导航栏，单击**域名管理**。

3.  在**域名管理**页面，单击目标域名对应的**管理**。

4.  在指定域名的左侧导航栏，单击**缓存配置**。

5.  单击**自定义HTTP响应头**。

6.  在**自定义HTTP响应头**页签，单击**添加**。

7.  配置HTTP响应头的参数和取值。

    目前阿里云CDN加速提供10个HTTP响应头参数可供您自定义取值，参数解释如下表所示。 如果您有其他HTTP头设置需求，请[提交工单](https://selfservice.console.aliyun.com)处理。

    **说明：** 增加HTTP响应头时您可以设置**是否允许重复**。**允许**表示允许重复，即源站返回的头会保留，同时会加上一个同名的头。**不允许**表示不允许重复，即源站返回的头会被新配置的同名头覆盖。

    ![HTTP头设置](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/1569282061/p69929.png)

    |参数|描述|示例|
    |:-|:-|--|
    |Content-Type|指定客户端程序响应对象的内容类型。|image|
    |Cache-Control|指定客户端程序请求和响应遵循的缓存机制。|no-cache|
    |Content-Disposition|指定客户端程序把请求所得的内容存为一个文件时提供的默认的文件名。|123.txt|
    |Content-Language|指定客户端程序响应对象的语言。|zh-CN|
    |Expires|指定客户端程序响应对象的过期时间。|Wed, 21 Oct 2015 07:28:00 GMT|
    |Access-Control-Allow-Origin|指定允许的跨域请求的来源。|\* **说明：** 您可以填写`*`表示全部域名；也可以填写完整域名，例如`www.aliyun.com`。 |
    |Access-Control-Allow-Headers|指定允许的跨域请求的字段。|X-Custom-Header|
    |Access-Control-Allow-Methods|指定允许的跨域请求方法。|POST、GET**说明：** 如果您需要同时添加POST和GET，请使用英文逗号（,）隔开。 |
    |Access-Control-Max-Age|指定客户端程序对特定资源的预取请求返回结果的缓存时间。|600|
    |Access-Control-Expose-Headers|指定允许访问的自定义头信息。|Content-Length|

8.  单击**确定**。

    在**自定义HTTP响应头**列表中，您可以单击**修改**或**删除**，对当前配置的HTTP响应头进行相应操作。


