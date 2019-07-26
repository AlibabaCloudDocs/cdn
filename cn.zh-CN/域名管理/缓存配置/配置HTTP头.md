# 配置HTTP头 {#task_261642 .task}

HTTP消息头准确描述了正在获取的资源、服务器或客户端的行为，定义了HTTP事务中的具体操作参数。通过本文档，您可以了解设置HTTP头响应的操作方法。

HTTP消息头是指，在超文本传输协议（ Hypertext Transfer Protocol，HTTP）的请求和响应消息中，协议头部的组件。

在HTTP消息头中，按其出现的上下文环境，分为通用头、请求头、响应头等。目前阿里云CDN提供10个HTTP响应头参数可供您自行定义取值，参数解释如下表所示。

|参数|描述|
|:-|:-|
|Content-Type|指定客户端程序响应对象的内容类型。|
|Cache-Control|指定客户端程序请求和响应遵循的缓存机制。|
|Content-Disposition|指定客户端程序把请求所得的内容存为一个文件时提供的默认的文件名。|
|Content-Language|指定客户端程序响应对象的语言。|
|Expires|指定客户端程序响应对象的过期时间。|
|Access-Control-Allow-Origin|指定允许的跨域请求的来源。|
|Access-Control-Allow-Headers|指定允许的跨域请求的字段。|
|Access-Control-Allow-Methods|指定允许的跨域请求方法。|
|Access-Control-Max-Age|指定客户端程序对特定资源的预取请求返回结果的缓存时间。|
|Access-Control-Expose-Headers|指定允许访问的自定义头信息。|

配置HTTP响应头时，注意事项如下：

-   HTTP响应头的设置会影响该加速域名下所有资源，当您通过客户端（例如浏览器）访问资源时，会影响其响应行为，但不会影响CDN缓存服务器行为。
-   目前仅支持上述HTTP头设置。如果您有其他HTTP头设置需求，请[提交工单](https://selfservice.console.aliyun.com)反馈。
-   关于参数Access-Control-Allow-Origin的取值，您可以填写`*`表示全部域名；也可以填写完整域名，例如`www.aliyun.com`。
-   目前不支持泛域名设置。

1.  登录[CDN控制台](https://cdn.console.aliyun.com)。
2.  在左侧导航栏，单击**域名管理**。
3.  在域名管理页面，单击目标域名对应的**管理**。
4.  在指定域名的左侧导航栏，单击**缓存配置**。
5.  单击**HTTP头**。
6.  在HTTP头设置页签，单击**添加**。 

    ![HTTP头设置](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5149/15641411427278_zh-CN.png)

7.  配置HTTP头的参数和取值。
8.  单击**确认**，配置成功。 

    您也可以单击**修改**或**删除**，对当前配置的HTTP头进行相应操作。


