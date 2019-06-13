# DNSPod配置CNAME {#task_187634 .task}

本文为您介绍了如何在腾讯云配置（原DNSPod）配置CNAME。如果您想启用CDN加速服务，您需要将加速域名指向CDN节点的CNAME地址，这样访问加速域名的请求才能转发到CDN节点上，达到加速效果。

1.  获取加速域名的CNAME地址。 
    1.  登录[CDN控制台](https://cdn.console.aliyun.com)。
    2.  进入域名管理页面，复制加速域名对应的CNAME值。 

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5113/156041352045282_zh-CN.png)

2.  添加CNAME记录。 
    1.  登录DNSPod（腾讯云）的**域名解析控制台**。
    2.  在对应域名的域名解析页，选择**添加记录**。
    3.  进行相关配置。 

        -   记录类型：选择**CNAME**。
        -   主机记录：即加速域名的前缀。例如：您的加速域名为`testcdn.aliyun.com`，那么前缀为`testcdn`。
        -   记录值：填写为步骤1复制的CNAME值。
        -   解析线路：默认值。
        -   TTL：默认值。
        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5114/156041352045300_zh-CN.png)

3.  单击**保存**，配置CNAME完毕。CNAME配置生效后，CDN服务立即生效。 
    -   CNAME配置生效时间：新增CNAME记录会实时生效，而修改CNAME记录需要最多72小时生效时间。
    -   添加时如果您遇到添加冲突，可考虑换一个加速域名，或者您也可以调整记录，详情请参见[解析记录冲突](https://help.aliyun.com/knowledge_detail/39787.html)。
    -   配置完CNAME后，由于状态更新约有10分钟延迟，阿里云CDN控制台的域名列表可能仍提示未配置CNAME，请您忽略即可。
4.  验证CNAME配置是否生效。 

    配置CNAME后，不同的DNS服务商CNAME生效的时间也不同。您可以通过输入`ping`或`dig`您所添加的加速域名来验证，如果被转向`*.*kunlun*.com`，即表示CNAME配置已经生效，CDN功能也已生效。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5113/15604135206060_zh-CN.png)


