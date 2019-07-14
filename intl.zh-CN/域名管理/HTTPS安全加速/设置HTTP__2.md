# 设置HTTP/2 {#task_261642 .task}

通过本文档，您可以了解HTTP/2协议的概念、优势和设置方法。

开启HTTP/2功能前，您需要确保已经成功配置HTTPS证书，操作方法请参见[配置HTTPS证书](intl.zh-CN/域名管理/HTTPS安全加速/配置HTTPS证书.md#)。

**说明：** 

-   如果您是第一次配置HTTPS证书，则需要等证书配置完成且生效后，才能开启HTTP/2。
-   如果您开启HTTP/2后，关闭了HTTPS证书功能，HTTP/2会自动失效。

HTTP/2也被称为HTTP 2.0，是最新的HTTP协议。目前，Chrome、 IE11、Safari和Firefox等主流浏览器已经支持HTTP/2协议。HTTP/2优化了性能，兼容了HTTP/1.1的语义，与SPDY相似，与HTTP/1.1有巨大区别。

HTTP/2的优势：

-   二进制协议：相比于HTTP 1.x基于文本的解析，HTTP/2将所有的传输信息分割为更小的消息和帧，并对它们采用二进制格式编码。基于二进制可以使协议有更多的扩展性，例如，引入帧来传输数据和指令。
-   内容安全：HTTP/2基于HTTPS，具有安全特性。使用HTTP/2特性可以避免单纯使用HTTPS引起的性能下降问题。
-   多路复用（MultiPlexing）：通过该功能，在一条连接上，您的浏览器可以同时发起无数个请求，并且响应可以同时返回。另外，多路复用中支持了流的优先级（Stream dependencies）设置，允许客户端告知服务器最优资源，可以优先传输。
-   Header压缩（Header compression）：HTTP请求头带有大量信息，而且每次都要重复发送。HTTP/2采用HPACK格式进行压缩传输，通讯双方各自缓存一份头域索引表，相同的消息头只发送索引号，从而提高效率和速度。
-   服务端推送（Server push）：同SPDY一样，HTTP/2也具有客户端推送功能。目前，大多数网站已经启用HTTP/2，如淘宝。使用浏览器Chrome登录控制台，您可以查看是否启用HTTP/2。

    **说明：** SPDY是Google开发的基于TCP的应用层协议，用以最小化网络延迟，提升网络速度，优化用户的网络体验。SPDY并不是一种用于替代HTTP的协议，而是对HTTP协议的增强。新协议的功能包括：数据流的多路复用、请求优先级和HTTP报头压缩，与HTTP/2相似。


1.  登录[CDN控制台](https://cdn.console.aliyun.com)。
2.  单击**域名管理**。
3.  在域名管理页面，单击目标域名后的**管理**。
4.  单击**HTTPS配置**。
5.  在**HTTP/2设置**页签，打开**HTTP/2**开关，开启该功能。 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5137/156310404647106_zh-CN.png)


