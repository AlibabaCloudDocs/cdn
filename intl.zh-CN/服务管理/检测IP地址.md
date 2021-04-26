---
keyword: [诊断工具, CDN工具, IP检测]
---

# 检测IP地址

阿里云CDN为您提供IP地址检测功能，您可以通过该功能检测指定的IP地址是否为阿里云CDN节点的IP，以及IP所属地域和运营商。

## 操作步骤

1.  登录[CDN控制台](https://cdn.console.aliyun.com)。

2.  在左侧导航栏，单击**工具服务**。

3.  在**IP地址检测**文本框中，输入您需要检测的IP地址，单击**检测**。

    **说明：** 支持检测IPv4和IPv6地址，一次只能检测一个IP。

    ![IP检测](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6679609161/p51480.png)

4.  查看检测结果。

    -   如果您检测的IP地址为CDN节点IP，检测结果会显示**地区**、**运营商**和**是否是CDN节点**。

        ![IP检测结果](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/7332609161/p51482.png)

    -   如果您检测的IP地址不是CDN节点IP，检测结果会提示**没有查询到符合条件的记录**。

## 相关API

[DescribeIpInfo](/intl.zh-CN/新版API参考/辅助工具类接口/验证IP是否为CDN节点.md)

