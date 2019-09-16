# 通过OSS控制台实现 {#task_828194 .task}

通过本文您可以详细了解，在OSS控制台上实现CDN加速OSS的操作方法。

执行本文操作之前，请确保您已完成阿里云[账号注册](https://account.alibabacloud.com/register/intl_register.htm)和[实名认证](https://account-intl.console.aliyun.com/#/intlAuth)。

1.  登录[OSS 管理控制台](https://oss.console.aliyun.com/overview)。
2.  在左侧**存储空间**列表中，单击目标存储空间名称。 

    ![OSS控制台](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/669803/156860457850559_zh-CN.png)

3.  单击**域名管理** \> **绑定用户域名**，打开绑定用户域名页面。 

    ![绑定用户域名](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/615645/156860458049828_zh-CN.png)

4.  设置绑定用户域名信息。 

    |参数|说明|
    |--|--|
    |用户域名|输入用户域名，例如：hello-world.com。|
    |自动添加CNAME记录|添加的域名是您当前阿里云账号下管理的域名，可以自动添加CNAME记录；非本账号下的域名，需要在域名解析商处手动配置云解析，操作方法请参考[阿里云/万网配置流程](../intl.zh-CN/快速入门/配置CNAME/阿里云__万网配置流程.md#)、[DNSPod配置流程](../intl.zh-CN/快速入门/配置CNAME/DNSPod配置流程.md#)或[新网配置流程](../intl.zh-CN/快速入门/配置CNAME/新网配置流程.md#)。|

5.  单击**提交**。 

    **说明：** 

    -   如果提示域名冲突，则表示该域名已被其他用户绑定。您可以单击获取TXT，通过添加域名TXT 记录来验证域名所有权，强制绑定域名。此操作会解除域名与之前存储空间的绑定。
6.  域名信息更新完成后，单击**域名绑定配置**，查看**阿里云 CDN 域名**和 **OSS 访问域名**。 

    **说明：** 域名信息更新约需要一分钟时间。


