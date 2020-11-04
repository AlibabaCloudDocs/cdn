---
keyword: [DNSPod, CNAME]
---

# DNSPod配置流程

本文为您介绍了如何在DNSPod配置CNAME。如果您想启用CDN加速服务，您需要将加速域名指向CDN节点的CNAME地址，这样访问加速域名的请求才能转发到CDN节点上，达到加速效果。

1.  获取加速域名的CNAME地址。

    1.  登录[CDN控制台](https://cdn.console.aliyun.com)。

    2.  在左侧导航栏，单击**域名管理**。

    3.  进入**域名管理**页面，复制加速域名对应的CNAME值。

        ![域名管理](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/0211008951/p66555.png)

2.  添加CNAME记录。

    1.  登录DNSPod的**域名解析控制台**。

    2.  在对应域名的域名解析页，选择**添加记录**。

    3.  进行相关配置。

        **说明：** 一个加速域名对应一个CNAME地址，主域名的CNAME地址不能被二级域名使用。如果您需要加速二级域名，需将二级域名也添加到CDN上，并解析到对应的CNAME地址，或者在CDN上添加泛域名，泛域名的CNAME可以被二级域名使用。

        -   记录类型：选择**CNAME**。
        -   主机记录：即加速域名的前缀。例如：您的加速域名为`testcdn.aliyun.com`，那么前缀为`testcdn`。
        -   记录值：填写为步骤1复制的CNAME值。
        -   解析线路：默认值。
        -   TTL：默认值。
    4.  单击**保存**。

        成功配置CNAME且生效后，加速服务会立即生效。

        **说明：**

        -   新增CNAME记录实时生效，修改CNAME记录在72小时内生效。
        -   成功配置CNAME后状态更新约有10分钟延迟，控制台的域名列表页可能仍提示“未配置CNAME”，请您暂时忽略。
3.  验证CNAME配置是否生效。

    1.  打开Windows的CMD命令行程序。

    2.  在命令行中ping加速域名，如果返回的解析结果和CDN控制台上该加速域名的CNAME值一致，则表示CDN加速已经生效。

        ![CNAME生效验证](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/6423839951/p66693.png)


