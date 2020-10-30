# 通过CDN控制台配置EdgeScript

边缘脚本用于支持CDN的可编程配置化。通过边缘脚本，您可以快速实现CDN的定制化业务需求。在CDN控制台上，您也可以根据边缘脚本定义的代码规则，创建边缘脚本规则，并发布到生产环境，实现对CDN产品的定制化管理。本文为您介绍了在CDN控制台上配置边缘脚本操作方法。

EdgeScript是为CDN设计的专用脚本，具有强大领域操控能力的同时，仍然保持简单易学的语法。通过EdgeScript，您可以快速构建基于阿里云CDN的个性化业务体系，全网秒级生效，敏捷的业务迭代会持续地为您赢得交付收益。

在CDN控制台上配置边缘脚本规则的流程，如下图所示。

![在CDN控制台上配置边缘脚本规则流程](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/5349174951/p65439.png)

1.  登录[CDN控制台](https://cdn.console.aliyun.com)。

2.  在左侧导航栏，单击**域名管理**

3.  在**域名管理**页面，单击域名右侧的**管理**。

4.  单击**边缘脚本**。

5.  添加规则到模拟环境。

    1.  在**模拟环境**页面，单击**添加规则**。

        **说明：** 目前单个域名仅支持添加一条边缘脚本规则。如果您需要添加多条规则，请[提交工单](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex)申请。

        ![模拟环境](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/5349174951/p65161.png)

    2.  根据界面提示，配置规则。

        ![配置规则](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/5349174951/p98082.png)

        边缘脚本参数配置规则，详情请参见[规则字段说明](/intl.zh-CN/边缘脚本/简介/原理介绍.md)。

        您可以按照使用场景编写规则代码，详情请参见[EdgeScript场景示例](/intl.zh-CN/边缘脚本/EdgeScript场景示例.md)。

    3.  单击**发布到模拟环境**完成添加。

6.  在模拟环境中，测试规则。

    模拟环境测试IP地址（该IP地址请以实际页面显示为准），如下图红框所示。

    ![测试IP](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/6349174951/p65164.png)

    在客户端路径C:\\Windows\\System32\\drivers\\etc中找到文件hosts。将模拟环境测试IP地址添加到hosts文件中。

7.  测试完成后，单击**发布所有规则到生产环境**，将模拟环境规则发布至生产环境。

    **说明：** 模拟环境规则发布到生产环境后，模拟环境的规则自动被清空。

    ![发布所有规则到生成环境](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/6349174951/p65390.png)

8.  如果您需要基于最新发布的规则进行增改，则需要将发布到生产环境的规则同步到模拟环境后再执行操作。 单击**从生产环境复制规则**，将发布到生产环境的规则同步到模拟环境。

    ![从生成环境复制规则](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/6349174951/p65389.png)

    生产环境的规则同步到模拟环境后，即可在模拟环境进行修改或新增规则，如下图所示。

    ![编辑模拟环境规则](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/6349174951/p65397.png)


