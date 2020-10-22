# Integrate Alibaba Cloud CDN with Anti-DDoS

Alibaba Cloud Content Delivery Network \(CDN\) integrates with Anti-DDoS to mitigate DDoS attacks for accelerated domain names. This topic describes how to set parameters in the Alibaba Cloud CDN console to integrate Alibaba Cloud CDN with Anti-DDoS.

An Anti-DDoS instance is created. You can purchase Anti-DDoS instances in the [Anti-DDoS console](https://yundun.console.aliyun.com/?p=ddosbgp#/ddosbasic/cn-hangzhou).

You can use this feature if you require content delivery acceleration and DDoS mitigation at the same time. After this feature is activated, network traffic of your workloads is automatically redirected from Alibaba Cloud CDN to Anti-DDoS when attacks are detected. When DDoS attacks stop, network traffic is automatically switched back to Alibaba Cloud CDN.

This feature is available in public preview and primarily targeted at users in the finance, retail, transportation, media, and government sectors. You can join the DingTalk group 32615821 to request customer support.

This feature can be applied, including but not limited to the following scenarios:

-   Finance

    Ensures the high availability \(HA\) of services and improves the experience of users across countries. Protects user information, transactions, and data assets to minimize the risks caused by attacks.

-   Retail

    Accelerates the delivery of website content, services of e-commerce, ticketing platforms, and collaborative software. Mitigates attacks to ensure the availability of services.

-   Media

    Accelerates the delivery of media content. Provides protection against service disruptions caused by workload spikes or attacks.


1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the Domain Names page, find the target domain name and click **Manage**.

4.  Choose **Security Settings** \> **DDoS Interaction**.

    If this feature is not activated under your account, click **Activate Now** to join the DingTalk group to request customer support.

5.  Turn on the **Anti-DDoS Interaction** switch.

6.  Set the **Associated Anti-DDoS Service**, **Association Type**, and **Target** parameters.

    ![Integrate CDN with Anti-DDoS](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/3920652061/p113561.png)

    **Note:** This message may appear: No Anti-DDoS Pro/Premium settings are found for the specified domain name.

    -   If you have not purchased any Anti-DDoS instance, you must purchase an Anti-DDoS instance in the [Anti-DDoS console](https://yundun.console.aliyun.com/?p=ddosbgp#/ddosbasic/cn-hangzhou).
    -   If you have already purchased an Anti-DDoS instance, you must configure the Anti-DDoS instance in the [Anti-DDoS console](https://yundun.console.aliyun.com/?p=ddosbgp#/ddosbasic/cn-hangzhou) to have your domain name protected.
7.  Click **OK**.


On the **DDoS Interaction** tab, check whether the settings are effective.

![ddos-2](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/3448958951/p113576.png)

After you enable this feature, Alibaba Cloud CDN automatically creates the following service linked role in Resource Access Management \(RAM\): AliyunServiceRoleForCDNAccessingDDoS. Alibaba Cloud CDN can assume this role to access Anti-DDoS resources. AliyunServiceRoleForCDNAccessingDDoS has the following permissions:

-   DescribeDomainAttackEvents: Queries events of attacks launched against a website.
-   DescribeDomainDDoSAttackEvents: Queries events of DDoS attacks.
-   DescribeDDoSEvents: Queries events of attacks launched against one or more Anti-DDoS Pro or Anti-DDoS Premium instances.
-   DescribeWebRules: Queries the forwarding rules of a website.
-   DescribeDomainQPSList: Queries the number of queries \(QPS\) of a website.
-   DescribeCdnLinkageRules: Queries the parameters set for the integration of Alibaba Cloud CDN and Anti-DDoS.

If you want to delete AliyunServiceRoleForCDNAccessingDDoS, you must disable the integration of Alibaba Cloud CDN and Anti-DDoS for all accelerated domain names. You can then delete the role in the RAM console. For more information, see [Service linked roles](/intl.en-US/RAM Role Management/Service linked roles.md).

