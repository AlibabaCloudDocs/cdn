# 配置UA黑白名单 {#task_371735 .task}

您可以通过配置UsageAgent黑名单和白名单来实现对访客身份的识别和过滤，从而限制访问CDN资源的用户，提升CDN的安全性。通过本文您可以了解UsageAgent黑/白名单的配置方法。

当您需要根据请求的UsageAgent字段进行访问控制时，请配置UsageAgent黑/白名单功能，实现对请求过滤。

-   UsageAgent黑名单：黑名单内的UsageAgent字段均无法访问当前资源。

    如果您的UsageAgent字段被加入黑名单，该带有UsageAgent字段的请求仍可访问到CDN节点，但是会被CDN节点拒绝并返回403，CDN日志中仍会记录这些黑名单中的UsageAgent字段请求记录。

-   UsageAgent白名单：只有白名单内的UsageAgent字段才能访问当前资源，白名单以外的UsageAgent字段均无法访问当前资源。

1.  登录[CDN控制台](https://cdn.console.aliyun.com)。
2.  在左侧导航栏，单击**域名管理**。
3.  在域名管理页面，单击目标域名对应的**管理**。
4.  在指定域名的左侧导航栏，单击**访问控制**。
5.  在右侧域名管理区域，单击**UA黑/白名单**。
6.  在UA黑/白名单页签，单击**修改配置**。 

    ![UA黑白名单](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/301857/156653360550946_zh-CN.png)

7.  根据界面提示，配置UsageAgent的**黑名单**或**白名单**。 

    |参数|说明|
    |--|--|
    |名单类型| UsageAgent名单类型如下：

    -   黑名单

黑名单内的UsageAgent字段均无法访问当前资源。

    -   白名单

只有白名单内的UsageAgent字段能访问当前资源，白名单以外的UsageAgent字段均无法访问当前资源。

 黑名单和白名单互斥，同一时间只支持其中一种方式生效。

 |
    |规则|配置UsageAgent字段时，用|分割多个值，支持通配符号\*。例如：\*curl\*|\*IE\*|\*chrome\*|\*firefox\*|

8.  单击**确定**。

