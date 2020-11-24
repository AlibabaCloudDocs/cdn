---
keyword: [黑白名单, UserAgent]
---

# 配置UA黑白名单

您可以配置UserAgent黑名单和白名单实现对访客身份的识别和过滤，从而限制访问CDN资源的用户，提升CDN的安全性。本文为您介绍UserAgent黑白名单的配置方法。

当您需要根据HTTP请求头中的UserAgent字段进行访问控制时，请配置UserAgent黑白名单功能，实现对请求的过滤。

-   UserAgent黑名单：黑名单内的UserAgent字段均无法访问当前资源。

    如果您的UserAgent字段被加入黑名单，该带有UserAgent字段的请求仍可访问到CDN节点，但是会被CDN节点拒绝并返回403，CDN日志中仍会记录这些黑名单中的UserAgent字段请求记录。

-   UserAgent白名单：只有白名单内的UserAgent字段才能访问当前资源，白名单以外的UserAgent字段均无法访问当前资源。

1.  登录[CDN控制台](https://cdn.console.aliyun.com)。

2.  在左侧导航栏，单击**域名管理**。

3.  在**域名管理**页面，单击目标域名对应的**管理**。

4.  在指定域名的左侧导航栏，单击**访问控制**。

5.  单击**UA黑/白名单**页签。

6.  在**UA黑/白名单**页签下，单击**修改配置**。

7.  根据界面提示，配置UserAgent的**黑名单**或**白名单**。

    ![UA黑/白名单](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/1201816061/p64289.png)

    |参数|说明|
    |--|--|
    |**名单类型**|UserAgent名单类型如下：

    -   黑名单

黑名单内的UserAgent字段均无法访问当前资源。

    -   白名单

只有白名单内的UserAgent字段能访问当前资源，白名单以外的UserAgent字段均无法访问当前资源。

**说明：** 黑名单和白名单互斥，同一时间只支持其中一种方式生效。 |
    |**规则**|配置UserAgent字段时，用竖线（\|）分割多个值，支持通配符号（\*）。例如：\*curl\*\|\*IE\*\|\*chrome\*\|\*firefox\*。 **说明：** 如果UA请求头为空，则可以使用`^$`表示。 |

8.  单击**确定**，完成配置。


