---
keyword: [回源HTTP请求头, 回源]
---

# 配置回源HTTP请求头

HTTP消息头准确描述了正在获取的资源、服务器或客户端的行为，定义了HTTP事务中的具体操作参数。如果您的回源业务逻辑需要通过配置HTTP请求头来实现时，可以阅读本文了解如何添加、修改或删除回源HTTP请求头。

HTTP消息头是指在超文本传输协议（ Hypertext Transfer Protocol，HTTP）的请求和响应消息中，协议头部的组件。在HTTP消息头中，按其出现的上下文环境，分为通用头、请求头、响应头等。

![HTTP消息头](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/3764788951/p87913.png)

**说明：** 目前CDN提供了新版的配置回源HTTP请求头功能，具体操作，请参见[配置回源HTTP请求头（新）](/intl.zh-CN/域名管理/回源配置/配置回源HTTP请求头（新）.md)。

1.  登录[CDN控制台](https://cdn.console.aliyun.com)。

2.  在左侧导航栏，单击**域名管理**。

3.  在**域名管理**页面，单击目标域名对应的**管理**。

4.  在指定域名的左侧导航栏，单击**回源配置**。

5.  单击**回源HTTP请求头**页签。

6.  单击**添加**。

7.  在**回源HTTP头**页面，选择**自定义回源头**，设置**自定义参数**和**取值**。

    **说明：** 当您在配置**回源HTTP头**时，建议选择**参数**为**自定义参数**，根据您的实际需求自定义HTTP头。

    ![回源HTTP头](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8888869161/p49739.png)

    如果要修改或删除已添加的参数，可以单击对应参数操作列表下的**修改**或**删除**。

8.  单击**确定**。


## 后续操作

当您在配置**回源HTTP头**时，如果选择**参数**为**自定义参数**，则配置自定义参数后，系统可能报错，如下图所示。原因是您配置的字段是内部保留字段，请您重新配置。

![配置自定义回源HTTP头错误页面](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/7664788951/p62269.png)

**相关文档**  


[批量配置域名](/intl.zh-CN/新版API参考/域名管理类接口/批量配置域名.md)

