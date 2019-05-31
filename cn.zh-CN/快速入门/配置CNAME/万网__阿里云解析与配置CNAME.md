# 万网/阿里云解析与配置CNAME {#task_187531 .task}

您在CDN中添加域名后，阿里云CDN会给您分配对应的CNAME地址。如果您想启用CDN加速服务，需要将加速域名指向CNAME地址，因此访问加速域名的请求才能转发到CDN节点上，达到加速效果。本文档以您的域名在阿里云解析（原万网）为例。

1.  获取加速域名的CNAME地址。 
    1.  登录[CDN控制台](https://cdn.console.aliyun.com)。
    2.  进入域名管理页面，复制加速域名对应的CNAME值。 

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5113/155928698545282_zh-CN.png)

2.  添加CNAME记录。 
    1.  登录 [域名解析控制台](https://dc.console.aliyun.com/dns/?spm=5176.200001.0.0.pbY4Je)。
    2.  进入域名解析页面，在您需要设置的域名后面，单击**解析设置**。 

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5113/155928698545284_zh-CN.png)

    3.  单击**添加记录**，添加CNAME记录。 

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5113/155928698545285_zh-CN.png)

        -   记录类型：选择`CNAME`。
        -   主机记录：加速域名的前缀。

            |如果您的加速域名为...|主机记录为...|
            |:-----------|:-------|
            |`testcdn.aliyun.com`|`testcdn`|
            |`www.aliyun.com`|`www`|
            |`aliyun.com`|`@`|
            |`*.aliyun.com`|`*`|

        -   记录值：您进行步骤1时复制的CNAME值。
        -   解析线路：默认值。
        -   TTL：默认值。
    4.  单击**确认**，配置CNAME完毕。CNAME配置生效后，CDN服务也会立即生效。 

        **说明：** 

        -   新增CNAME记录会实时生效，修改CNAME记录72小时之内生效。
        -   配置完CNAME后，由于状态更新约有10分钟延迟，阿里云CDN控制台的域名列表页可能仍提示“未配置CNAME”，请您暂时忽略。
3.  验证CNAME配置是否生效。 

    配置CNAME后，不同的DNS服务商CNAME配置生效的时间也不同。您可以通过输入`ping`或`dig`您所添加的加速域名来验证，如果被转向`*.*kunlun*.com`，即表示CNAME配置已经生效，CDN功能也已生效。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5113/155928698545287_zh-CN.png)

    另外我们还为您提供域名在DNSPod和新网配置CNAME，详情请参见[DNSPod配置CNAME](intl.zh-CN/快速入门/配置CNAME/DNSPod配置CNAME.md#)和[新网配置CNAME](intl.zh-CN/快速入门/配置CNAME/新网配置CNAME.md#)。


