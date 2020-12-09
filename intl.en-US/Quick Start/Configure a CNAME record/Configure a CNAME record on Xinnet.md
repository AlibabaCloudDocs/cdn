---
keyword: [CNAME, Xinnet]
---

# Configure a CNAME record on Xinnet

This topic describes how to configure a Canonical Name \(CNAME\) record for a domain name on Xinnet. To enable Alibaba Cloud Content Delivery Network \(CDN\) for a domain name, you must add a CNAME record to map the domain name to the CNAME assigned by Alibaba Cloud CDN. This way, requests destined for the domain name can be redirected to CDN nodes.

1.  Obtain the CNAME assigned to the domain name.

    1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

    2.  In the left-side navigation pane, click **Domain Names**.

    3.  On the **Domain Names** page, copy the CNAME of the domain name.

        ![Domain Names](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3630062061/p66555.png)

2.  Add a CNAME record for the domain name.

    1.  Log on to the **DNS console** of Xinnet. Find the domain name that you want to manage, navigate to the **Manage DNS** page, and then click **Add Record**.

        **Note:** Each CNAME can be mapped to only one domain name. The CNAME of a top-level domain name cannot be mapped to its second-level domain names. If you need to accelerate a second-level domain name, add the domain name to Alibaba Cloud CDN. Alibaba Cloud then assigns a CNAME to the domain name. Alternatively, you can add a second-level wildcard domain name to Alibaba Cloud CDN. Domain names that match the wildcard domain name can be mapped to the CNAME of the wildcard domain name.

        -   Type: Select `CNAME` from the drop-down list.
        -   Host: Enter the prefix of the domain name.

            |Domain name|Host|
            |:----------|:---|
            |`testcdn.aliyun.com`|`testcdn`|
            |`www.aliyun.com`|`www`|
            |`aliyun.com`|`@`|
            |`*.aliyun.com`|`*`|

        -   ISP Line: Use the default value.
        -   Value: Enter the CNAME assigned to the domain name.
        -   TTL: Use the default value.
    2.  Click **Submit**.

        After the CNAME record takes effect, CDN acceleration is automatically enabled for the domain name.

        **Note:**

        -   After you add a CNAME record, it immediately takes effect. After you modify a CNAME record, the modifications take effect within 72 hours.
        -   After you add a CNAME record, it takes about 10 minutes for the system to update the status in the console. The system may prompt that you must add a CNAME record. Ignore the message.
3.  Check whether the CNAME record has taken effect.

    1.  Open the Command Prompt in Windows.

    2.  Use the Command Prompt to ping the domain name. If the CNAME in the output matches the CNAME assigned to the accelerated domain name in the Alibaba Cloud CDN console, it indicates that CDN acceleration is enabled for the domain name.

        ![Check whether the CNAME record has taken effect](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7423839951/p66693.png)


