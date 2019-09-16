# 过滤URL中可变参数 {#task_878912 .task}

当您的URL请求中带有queryString或其他可变参数时，资源重新回源时，会导致CDN缓存命中率降低。您可以针对可变参数开启参数过滤功能，提升资源的缓存命中率。

执行本文操作之前，请确保您已完成阿里云[账号注册](https://account.alibabacloud.com/register/intl_register.htm)和[实名认证](https://account-intl.console.aliyun.com/#/intlAuth)。

-   当您的URL请求中带有queryString时，或当CDN回源到私有读写类型的bucket，URL自动带上OSS私有访问需要的OSSAccessKeyId、Expires和Signature参数时，CDN默认对带有不同queryString的相同URL请求的处理方式不同，缓存也不同。如果queryString发生变化，则资源重新回源，会导致CDN缓存命中率降低。可以通过开启URL的参数过滤功能，提升资源的缓存命中率。
-   对于CDN加速OSS的场景，建议开启私有bucket回源功能。详细说明请参见[开启私有Bucket回源](../intl.zh-CN/域名管理/回源配置/开启私有Bucket回源授权.md#)。

1.  登录[CDN控制台](https://cdn.console.aliyun.com)。
2.  在左侧导航栏，单击**域名管理**。
3.  在域名管理页面，单击目标域名对应的**管理**。
4.  在指定域名的左侧导航栏，单击**性能优化**。
5.  在过滤参数区域，配置保留过滤参数和忽略参数。 
    -   保留过滤参数
        1.  单击**保留过滤参数**区域的**修改配置**。

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5161/156860494057056_zh-CN.png)

        2.  您可以根据所需配置**保留过滤参数**。

            |参数|说明|
            |--|--|
            |过滤参数|保留过滤参数开关。打开过滤参数开关后，资源回源时会去除URL中`?`之后的参数，提升文件缓存命中率。|
            |保留参数|配置需要保留的参数。最多可以配置10个保留参数，用空格作分隔符。|
            |保留回源参数|保留回源参数开关。打开保留回源参数开关后，资源回源时，保留所有参数。|

            示例说明：

            1.  CDN节点向源站发起请求`http://www.abc.com/a.jpg`，忽略参数x=1。
            2.  源站响应该请求内容后，响应到达CDN节点。
            3.  CDN节点会保留一份副本，然后继续向终端响应 `http://www.abc.com/a.jpg` 的内容。
            4.  所有类似的请求`http://www.abc.com/a.jpg?参数`均响应CDN副本`http://www.abc.com/a.jpg` 的内容。
        3.  单击**确定**。
    -   忽略参数
        1.  单击**忽略参数**区域的**修改配置**。

            ![过滤参数](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5161/15686049417304_zh-CN.png)

        2.  您可以根据所需配置**忽略参数**。

            |参数|说明|
            |--|--|
            |过滤参数|忽略过滤参数开关。打开过滤参数开关后，资源回源时会删除指定参数，剩余参数将不会被删除。|
            |忽略参数|配置需要忽略的参数。最多可以配置10个忽略参数，用空格作分隔符。|
            |保留回源参数|保留回源参数开关。打开保留回源参数开关后，资源回源时，保留所有参数。|

            示例说明：`http://www.abc.com/a.jpg?x=1`和`http://www.abc.com/a.jpg?x=2`会响应不同参数源站的响应内容。

        3.  单击**确定**。

