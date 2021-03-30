# EdgeScript快速入门

在CDN控制台上，您可以根据边缘脚本定义的代码规则，创建边缘脚本规则，并发布到生产环境，实现对CDN产品的定制化管理。本文为您介绍在CDN控制台上，如何配置使用边缘脚本。

## 使用流程

![1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/3701685161/p249648.png)

1.  登录[CDN控制台](https://cdn.console.aliyun.com)。

2.  在左侧导航栏，单击**域名管理**。

3.  在域名右侧，单击**管理**。

4.  单击**边缘脚本**。

5.  在模拟环境中添加规则。

    1.  在**模拟环境**页面，单击**添加规则**，配置边缘脚本规则。

        **说明：** 目前单个域名仅支持添加一条边缘脚本规则。如果您需要添加多条规则，请[提交工单](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex)申请。

        ![1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/3910756161/p249714.png)

        配置信息及说明，请参见下表：

        |配置信息|是否必填|说明|
        |----|----|--|
        |规则名称|是|规则名。仅支持英文字母、数字和下划线。|
        |规则代码|是|规则代码。        -   您可以直接输入规则代码，也可以单击**使用代码模板**，选择对应的场景代码模板。
        -   您可以按照使用场景编写规则代码。更多详情，请参见[EdgeScript场景示例](/intl.zh-CN/边缘脚本/EdgeScript场景示例.md)。 |
        |优先级|是|规则优先级。取值范围**0~999**，数值越大，优先级越高。|
        |执行位置|是|规则执行位置。更多详情，请参见[执行位置与优先级](/intl.zh-CN/边缘脚本/EdgeScript原理介绍.md)。|
        |启用状态|是|规则启用状态。|
        |Break|否|本规则命中情况下，是否终止本阶段剩余规则的执行。开启后，匹配该规则，停止执行其余的ESL规则。|
        |扩展项|否|当前支持扩展。目前仅支持`_es_dbg=signature`字段。|

    2.  单击**发布到模拟环境**。

6.  在模拟环境中，测试规则。

    模拟环境测试IP地址以实际页面显示为准，请参见下图：

    ![测试IP](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6349174951/p65164.png)

    在客户端路径C:\\Windows\\System32\\drivers\\etc中找到hosts文件。将模拟环境测试IP地址添加到hosts文件中。

7.  测试完成后，单击**发布所有规则到生产环境**，将模拟环境规则发布至生产环境。

    **说明：** 模拟环境规则发布到生产环境后，模拟环境的规则自动被清空。

    ![发布所有规则到生成环境](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6349174951/p65390.png)

8.  如果您需要基于最新发布的规则进行增改，则需要将发布到生产环境的规则同步到模拟环境后再执行操作。 单击**从生产环境复制规则**，将发布到生产环境的规则同步到模拟环境。

    ![从生成环境复制规则](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6349174951/p65389.png)

    生产环境的规则同步到模拟环境后，即可在模拟环境进行修改或新增规则，请参见下图。

    ![编辑模拟环境规则](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6349174951/p65397.png)


如果您喜欢CLI命令行界面，可以通过CLI工具使用边缘脚本。更多详情，请参见[通过CLI工具使用边缘脚本](/intl.zh-CN/边缘脚本/常见问题/通过CLI工具使用边缘脚本.md)。

