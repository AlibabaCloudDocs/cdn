# 配置边缘Web应用防火墙

CDN结合边缘Web应用防火墙 WAF（Web Application Firewall）能力，将业务流量进行恶意特征识别及防护，将正常、安全的流量回源到服务器。避免网站服务器被恶意入侵，保障业务的核心数据安全，解决因恶意攻击导致的服务器性能异常问题。 通过本文，您可以了解WAF防护功能、使用场景、费用说明和设置方法。

## 前提条件

-   您已在[CDN控制台](https://cdn.console.aliyun.com)开通WAF功能（开通方式：选择**选择边缘Web应用防火墙** \> **安全总览**，单击**开通基础版**）。
-   目前CDN仅支持中国内地加速节点的WAF防护，开启前请您确认域名的加速区域。修改域名加速区域的操作方法，请参见[修改基础信息](/cn.zh-CN/域名管理/基本配置/修改基础信息.md)。

## 背景信息

阿里云CDN的WAF功能，是指CDN融合了WAF能力，在CDN节点上，提供WAF防护功能。WAF防护具体功能，请参见[什么是Web应用防火墙](/cn.zh-CN/产品简介/什么是Web应用防火墙.md)。

CDN的WAF服务主要适用于金融、电商、O2O、互联网+、游戏、政府、保险等行业，保护您的网站在使用CDN加速的同时，免受因外部恶意攻击而导致的意外损失。

使用CDN WAF功能后，可以帮助您解决以下问题：

-   防数据泄密，避免因黑客的注入入侵攻击，导致网站核心数据被拖库泄露。
-   阻止木马上传网页篡改，保障网站的公信力。
-   提供虚拟补丁，针对网站被曝光的最新漏洞，最大可能地提供快速修复规则。

当您开启WAF功能后，CDN WAF会对此域名的所有请求进行检测，并按照账户维度，对域名开启WAF功能的请求次数汇总，然后收费。CDN WAF计费价格，请参见[增值服务计费-CDN WAF计费](https://www.aliyun.com/price/product?spm=a2c4g.11186623.2.10.1b444ee22Dxy8y#/cdn/detail)。

## 操作步骤

1.  登录[CDN控制台](https://cdn.console.aliyun.com)。

2.  在左侧导航栏，单击**域名管理**。

3.  在**域名管理**页面，单击目标域名对应的**管理**。

4.  在指定域名的左侧导航栏，单击**安全配置**。

5.  在**边缘Web应用防火墙**页签，打开**边缘Web应用防火墙-中国大陆**开关。

6.  单击**修改配置**。

7.  根据页面提示，配置**Web安全**和**访问控制/限流**。

    |项目|参数|说明|
    |--|--|--|
    |**Web安全**|**状态**|Web入侵防护开关。|
    |**模式**|Web入侵防护模式如下：    -   **拦截**：发现入侵后直接拦截。
    -   **告警**：发现入侵后只告警不拦截。 |
    |**防护规则组**|Web入侵防护规则如下：    -   **宽松规则**：当您发现在**中等规则**下存在较多误拦截时，建议您选择**宽松规则**。宽松模式下对业务的误报程度最低，但也容易漏过攻击。
    -   **中等规则**：默认使用中等规则。
    -   **严格规则**：当您需要更严格地防护路径穿越、SQL注入、命令执行时，建议您选择**严格规则**。 |
    |**解码设置**|设置需要正则防护引擎解码分析的内容格式。    1.  单击![jiema](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/3506924061/p178440.png)，打开配置窗口。
    2.  选中或取消选中要解码的格式。
        -   不支持取消的格式：**URL解码**、**JavaScript Unicode解码**、**Hex解码**、**注释处理**、**空格压缩**。
        -   支持取消的格式：**Multipart解析**、**JSON解析**、**XML解析**、**PHP序列化解码**、**HTML实体解码**、**UTF-7解码**、**Base64解码**、**Form解析**。
    3.  单击**确定**。
**说明：** 为保证防护效果，正则防护引擎默认对请求中所有格式类型的内容进行解码分析。如果您发现正则防护引擎经常对业务中包含指定格式内容的请求造成误拦截，您可以取消解码对应格式，针对性地降低误杀率。 |
    |**访问控制/限流**|**IP黑名单**|**状态**|IP黑名单控制开关。**说明：** IP黑名单支持一键封禁特定的IP地址和地址段访问，以及指定区域的IP地址的访问限制能力。您可以根据实际需求，单击**前去配置**，添加IP地址黑名单和IP地域黑名单。 |
    |**自定义防护策略**|**状态**|自定义防护策略开关。**说明：** 自定义防护策略支持自定义精准条件的访问控制规则，以及基于精准条件下的指定统计对象的访问限制自定义规则。您可以根据实际需求，单击**前去配置**，添加自定义防护策略。 |


## 角色授权

当您需要CDN边缘Web应用防火墙自动角色授权时，可以使用CDN WAF功能，CDN将自动为您创建AliyunServiceRoleForCDNAccessingWAF角色，并授权CDN使用该角色，并授权CDN访问WAF产品中的资源。

AliyunServiceRoleForCDNAccessingWAF角色中包含的权限包括如下接口：

-   DescribePayInfo
-   CreatePostpaidInstance
-   CreateOutputDomainConfig
-   DeleteOutputDomainConfig
-   DescribeDomainWebAttackTypePv
-   ModifyLogServiceStatus
-   DescribeProtectionModuleMode
-   DescribeDomainRuleGroup
-   DescribeRegions
-   ModifyProtectionRuleStatus
-   ModifyProtectionRuleCacheStatus
-   DescribePeakValueStatisticsInfo
-   DescribeDomainAccessStatus
-   DescribeFlowStatisticsInfo
-   DescribeDomainTotalCount
-   DescribeResponseCodeStatisticsInfo
-   DescribeDDosCreditThreshold
-   ModifyDomainClusterType
-   DescribeInstanceInfo
-   DescribeOutputDomains
-   CreateOutputDomain
-   DeleteOutputDomain
-   DeleteInstance
-   DescribeInstanceSpecInfo
-   DescribeDomainBasicConfigs

如果您希望删除该AliyunCDNAccessingWAFRole角色，您需要提交工单删除CDN WAF实例，关闭所有域名的CDN WAF功能，然后才能在RAM中删除该SLR。

