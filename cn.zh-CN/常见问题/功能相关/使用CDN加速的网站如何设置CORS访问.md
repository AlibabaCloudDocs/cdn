# 使用CDN加速的网站如何设置CORS访问 {#task_1715981 .task}

介绍使用CDN加速的网站如何设置CORS访问。

网站使用CDN加速后，如果某个CDN节点下先发生了非跨域的访问，CDN会缓存一个没有CORS头部的文件内容，在过期之前发生的跨域访问，会因为没有CORS头部信息而导致访问报错。这种情况可以利用CDN的自定义Header的方式设置CORS的头部信息的方式来避免。

1.  登录[CDN控制台](https://cdn.console.aliyun.com)。
2.  在左侧导航栏，单击**域名管理**。
3.  在域名管理页面，单击目标域名对应的**管理**。
4.  在指定域名的左侧导航栏，单击**缓存配置**。
5.  单击**HTTP头**。
6.  在HTTP头设置页签，单击**添加**。 

    ![HTTP头设置](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5149/15662629497278_zh-CN.png)

7.  根据需要设置**Access-Control-Allow-Origin**、**Access-Control-Allow-Methods** 和**Access-Control-Max-Age** 的头部信息。
8.  查看设置的CORS头部信息。 

    ![CORS头部设置结果](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5290/15662629493775_zh-CN.png)

    **说明：** CDN控制台上设置的CORS等头部信息对整个加速域名生效，会覆盖掉源站设置的头部信息。


