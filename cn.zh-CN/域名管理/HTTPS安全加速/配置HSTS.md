# 配置HSTS {#task_261642 .task}

通过开启HSTS（HTTP Strict Transport Security）功能，您可以强制客户端（如浏览器）使用HTTPS与服务器创建连接，降低第一次访问被劫持的风险。

执行该操作前，请您确保已成功配置HTTPS证书，操作方法请参见[配置HTTPS证书](cn.zh-CN/域名管理/HTTPS安全加速/配置HTTPS证书.md#)。

当您的网站全站使用HTTPS后，需要将所有HTTP请求的301和302重定向到HTTPS。如果您在浏览器输入或直接单击HTTP链接，则服务器会将该HTTP请求的301和302重定向到HTTPS。该操作过程可能被劫持，导致重定向后的请求未发送到服务器，该问题可以通过HSTS来解决。

HSTS是一个响应头：`Strict-Transport-Security: max-age=expireTime [; includeSubDomains] [; preload]`，参数说明如下表所示。

|参数|说明|
|--|--|
|max-age|单位是秒。|
|Strict-Transport-Security|在浏览器缓存的时间，浏览器处理域名的HTTP访问时，若该域名的Strict-Transport-Security没有过期，则在浏览器内部做一次307重定向到HTTPS，从而避免浏览器和服务器之间301/302重定向被劫持的风险。|
|includeSubDomains|可选参数。如果指定这个参数，说明这个域名所有子域名也适用上面的规则。|
|preload|可选参数，支持preload列表。|

**说明：** 

-   HSTS生效前，第一次需要将301和302重定向到HTTPS。
-   HSTS响应头在HTTPS访问的响应中有效，在HTTP访问的响应中无效。
-   仅对443端口有效，对其他端口无效。
-   仅对域名有效，对IP无效。

1.  登录[CDN控制台](https://cdn.console.aliyun.com)。
2.  在左侧导航栏，单击**域名管理**。
3.  在域名管理页面，单击目标域名对应的**管理**。
4.  在**HSTS**区域，单击**修改配置**。 

    ![HSTS设置](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/41680/156414069247911_zh-CN.png)

5.  在HSTS设置对话框，打开**HSTS开关**，配置过期时间和包含子域名。
6.  单击**确定**。

