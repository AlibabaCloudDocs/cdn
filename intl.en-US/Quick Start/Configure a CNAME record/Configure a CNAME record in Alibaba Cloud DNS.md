---
keyword: [CNAME, add a CNAME record on HiChina, CNAME mapping on HiChina, CNAME of Alibaba Cloud domain name]
---

# Configure a CNAME record in Alibaba Cloud DNS

After you add a domain name to Alibaba Cloud Content Delivery Network \(CDN\), Alibaba Cloud CDN assigns a Canonical Name \(CNAME\) to the domain name. To enable the CDN service for the domain name, you must add a CNAME record to map the accelerated domain name to the CNAME. This way, requests destined for the accelerated domain name can be redirected to the CDN nodes that are nearest to the clients. This topic describes how to configure a CNAME record for a domain name in Alibaba Cloud DNS.

1.  Obtain the CNAME assigned to the accelerated domain name.

    1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

    2.  In the left-side navigation pane, click **Domain Names**.

    3.  On the **Domain Names** page, copy the CNAME of the accelerated domain name.

        ![Click Domain Names](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/3630062061/p66555.png)

2.  Add a CNAME record for the accelerated domain name.

    1.  Log on to the [Alibaba Cloud DNS console](https://dc.console.aliyun.com/dns).

    2.  On the Manage DNS page, click the Domains tab, select the domain name that you want to manage, and then click **Configure** in the Actions column.

    3.  Click **Add Record** and add a CNAME record.

        ![Add a CNAME record](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/3630062061/p64412.png)

        -   Type: Select `CNAME` from the drop-down list.
        -   Host: Enter the prefix of the accelerated domain name.

            |Accelerated domain name|Host|
            |:----------------------|:---|
            |`testcdn.aliyun.com`|`testcdn`|
            |`www.aliyun.com`|`www`|
            |`aliyun.com`|`@`|
            |`*.aliyun.com`|`*`|

        -   ISP Line: Use the default value.
        -   Value: Enter the CNAME assigned to the accelerated domain name.
        -   TTL: Use the default value.
    4.  Click **OK**.

        The CNAME record is added. After the CNAME record takes effect, CDN acceleration is automatically enabled for the domain name.

        **Note:**

        -   After you add a CNAME record, it immediately takes effect. After you modify a CNAME record, the modifications take effect within 72 hours.
        -   After you add a CNAME record, it takes approximately 10 minutes for the system to update the status in the console. The system may prompt that you must add a CNAME record. Ignore the message.
3.  Check whether the CNAME record has taken effect.

    1.  Open the Command Prompt in Windows.

    2.  Use the Command Prompt to ping the accelerated domain name. If the CNAME in the output matches the CNAME assigned to the accelerated domain name in the Alibaba Cloud CDN console, it indicates that the CDN service is enabled for the domain name.

        ![Check whether the CNAME record has taken effect](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/7423839951/p66693.png)


