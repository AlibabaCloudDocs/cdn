# 配置CDN WAF

CDN结合边缘Web应用防火墙WAF（Web Application Firewall）能力，将业务流量进行恶意特征识别及防护，将正常、安全的流量回源到服务器。避免网站服务器被恶意入侵，保障业务的核心数据安全，解决因恶意攻击导致的服务器性能异常问题。 通过本文您可以了解WAF防护功能、使用场景、费用说明和设置方法。

## 前提条件

-   您已在[CDN控制台](https://cdn.console.aliyun.com)开通CDN WAF功能（开通方式：选择**CDN WAF** \> **安全总览**，单击**开通基础版**）。
-   基础版仅支持中国内地，开启加速节点的WAF防护前请您确认域名的加速区域选择为**仅中国内地**。修改域名加速区域的操作方法，请参见[修改基础信息](/cn.zh-CN/域名管理/基本配置/修改基础信息.md)。

## 增值服务

如果您是政府、金融、传媒、零售类客户或月消费金额大于2万，可联系您对应的阿里云销售，协助您开通CDN WAF的高级版或企业版。高级版或企业版相对于基础版提供更多的功能以及其特殊的商业模式，因此需要支付更高的费用，关于更多CDN WAF具体功能配置，请参见[Web应用防火墙](https://help.aliyun.com/product/28515.html?spm=a2c4g.11174283.6.69.1b097035Dyzr9S)，具体功能单击下表中链接即可。

|功能项|基础版|高级版|企业版|
|---|---|---|---|
|WEB扫描防护|[支持](https://help.aliyun.com/document_detail/147717.html)|[支持](https://help.aliyun.com/document_detail/147717.html)|[支持](https://help.aliyun.com/document_detail/147717.html)|
|主动防御|不支持|不支持|[支持](https://help.aliyun.com/document_detail/147941.html)|
|账号安全|不支持|[支持](https://help.aliyun.com/document_detail/147940.html)|[支持](https://help.aliyun.com/document_detail/147940.html)|
|CC攻击防护|不支持|[支持](https://help.aliyun.com/document_detail/147594.html)|[支持](https://help.aliyun.com/document_detail/147594.html)|
|海量IP黑名单封禁|[支持](https://help.aliyun.com/document_detail/147687.html)|[支持](https://help.aliyun.com/document_detail/147687.html)|[支持](https://help.aliyun.com/document_detail/147687.html)|
|Rate Limit|不支持|不支持|[支持](https://help.aliyun.com/document_detail/147937.html)|
|爬虫情报库|不支持|不支持|[支持](https://help.aliyun.com/document_detail/159911.html)|
|验证码集成|不支持|不支持|[支持](https://help.aliyun.com/document_detail/147937.html)|
|爬虫智能算法|不支持|不支持|[支持](https://help.aliyun.com/document_detail/159910.html)|
|基础Web攻击防护|[支持](https://help.aliyun.com/document_detail/147592.html)|[支持](https://help.aliyun.com/document_detail/147592.html)|[支持](https://help.aliyun.com/document_detail/147592.html)|
|0 DAY规则更新防护|[支持](https://help.aliyun.com/document_detail/147592.html)|[支持](https://help.aliyun.com/document_detail/147592.html)|[支持](https://help.aliyun.com/document_detail/147592.html)|
|预警\|阻断模式|[支持](https://help.aliyun.com/document_detail/147592.html)|[支持](https://help.aliyun.com/document_detail/147592.html)|[支持](https://help.aliyun.com/document_detail/147592.html)|
|解码防混淆编码绕过|不支持|[支持](https://help.aliyun.com/document_detail/147592.html)|[支持](https://help.aliyun.com/document_detail/147592.html)|
|规则组自定义|不支持|不支持|[支持](https://help.aliyun.com/document_detail/99477.html)|
|HTTP字段访问控制|不支持|[支持](https://help.aliyun.com/document_detail/42780.html)|[支持](https://help.aliyun.com/document_detail/42780.html)|
|日志服务|不支持|[支持](https://help.aliyun.com/document_detail/95078.html)（1T）|[支持](https://help.aliyun.com/document_detail/95078.html)（3T）|

## 背景信息

阿里云CDN的WAF功能，是指CDN融合了WAF能力，在CDN节点上，提供WAF防护功能。WAF防护具体功能，请参见[什么是Web应用防火墙](/cn.zh-CN/产品简介/什么是Web应用防火墙.md)。

CDN的WAF服务主要适用于金融、电商、O2O、互联网+、游戏、政府、保险等行业，保护您的网站在使用CDN加速的同时，免受因外部恶意攻击而导致的意外损失。

使用CDN WAF功能后，可以帮助您解决以下问题：

-   防数据泄密，避免因黑客的注入式攻击导致网站核心数据被拖库泄露。
-   阻止木马上传网页篡改，保障网站的公信力。
-   提供虚拟补丁，针对网站被曝光的最新漏洞，最大可能地提供快速修复规则。

当您开启WAF功能后，CDN WAF会对此域名的所有请求进行检测，并按照账户维度，对域名开启WAF功能的请求次数汇总，然后收费。CDN WAF计费价格，请参见[增值服务计费-CDN WAF计费](https://www.aliyun.com/price/product?spm=a2c4g.11186623.2.10.1b444ee22Dxy8y#/cdn/detail)。

## 操作步骤

1.  登录[CDN控制台](https://cdn.console.aliyun.com)。

2.  在左侧导航栏，选择**CDN WAF** \> **域名列表**。

3.  在**域名列表**页面，单击目标域名对应的**防护配置**。

4.  根据页面提示，配置**Web安全**、**Bot管理**和**访问控制/限流**。

    |项目|参数|说明|
    |--|--|--|
    |**Web安全**|**状态**|Web入侵防护开关。|
    |**模式**|Web入侵防护模式如下：    -   **拦截**：发现入侵后直接拦截。
    -   **告警**：发现入侵后只告警不拦截。 |
    |**防护规则组**|Web入侵防护规则如下：    -   **宽松规则**：当您发现在**中等规则**下存在较多误拦截时，建议您选择**宽松规则**。宽松模式下对业务的误报程度最低，但也容易漏过攻击。
    -   **中等规则**：默认使用中等规则。
    -   **严格规则**：当您需要更严格地防护路径穿越、SQL注入、命令执行时，建议您选择**严格规则**。 |
    |**解码设置**|设置需要正则防护引擎解码分析的内容格式。    1.  单击![jiema](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/3506924061/p178440.png)，打开配置窗口。
    2.  选中或取消选中要解码的格式。
        -   不支持取消的格式：**URL解码**、**JavaScript Unicode解码**、**Hex解码**、**注释处理**、**空格压缩**。
        -   支持取消的格式：**Multipart解析**、**JSON解析**、**XML解析**、**PHP序列化解码**、**HTML实体解码**、**UTF-7解码**、**Base64解码**、**Form解析**。
    3.  单击**确定**。
**说明：** 为保证防护效果，正则防护引擎默认对请求中所有格式类型的内容进行解码分析。如果您发现正则防护引擎经常对业务中包含指定格式内容的请求造成误拦截，您可以取消解码对应格式，针对性地降低误杀率。 |
    |**Bot管理（仅限企业版用户）**|**合法爬虫**|**状态**|合法爬虫开关。**说明：** 合法爬虫提供合法搜索引擎白名单（例如Google、Bing、百度、搜狗、360、Yandex等），可应用于全域名下放行。您可以根据实际需求，单击**前去配置**，启用或者关闭合法爬虫。 |
    |**典型爬虫行为识别**|**状态**|典型爬虫行为识别开关。**说明：** 典型爬虫行为识别提供典型爬虫行为识别的通用算法实例，可配置基本业务参数和风险阈值进行机器学习，输出智能防护结果以对抗高级爬虫。您可以根据实际需求，单击**前去配置**，添加算法规则。 |
    |**爬虫威胁情报**|**状态**|爬虫威胁情报开关。**说明：** 爬虫威胁情报基于云平台强大的计算能力，提供拨号池IP、IDC机房IP、恶意扫描工具IP以及云端实时模型生成的恶意爬虫库等多种维度的威胁情报，可应用于全域名或指定路径下进行阻断。您可以根据实际需求，单击**前去配置**，编辑情报。 |
    |**访问控制/限流**|**IP黑名单**|**状态**|IP黑名单控制开关。**说明：** IP黑名单支持一键封禁特定的IP地址和地址段访问，以及指定区域的IP地址的访问限制能力。您可以根据实际需求，单击**前去配置**，添加IP地址黑名单和IP地域黑名单。 |
    |**自定义防护策略**|**状态**|自定义防护策略开关。**说明：** 自定义防护策略支持自定义精准条件的访问控制规则，以及基于精准条件下的指定统计对象的访问限制自定义规则。您可以根据实际需求，单击**前去配置**，添加自定义防护策略。 |


