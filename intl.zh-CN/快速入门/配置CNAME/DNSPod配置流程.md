# DNSPod配置流程 {#task_187634 .task}

本文为您介绍了如何在腾讯云（原DNSPod）配置CNAME。如果您想启用CDN加速服务，您需要将加速域名指向CDN节点的CNAME地址，这样访问加速域名的请求才能转发到CDN节点上，达到加速效果。

1.  添加CNAME记录。 
    1.  登录DNSPod（腾讯云）的**域名解析控制台**。
    2.  在对应域名的域名解析页，选择**添加记录**。
    3.  进行相关配置。 

        -   记录类型：选择**CNAME**。
        -   主机记录：即加速域名的前缀。例如：您的加速域名为`testcdn.aliyun.com`，那么前缀为`testcdn`。
        -   记录值：填写为步骤1复制的CNAME值。
        -   解析线路：默认值。
        -   TTL：默认值。
        ![域名解析](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5114/156412954645300_zh-CN.png)

    4.  单击**保存**。 

