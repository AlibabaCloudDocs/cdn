---
keyword: [DNSPod, CNAME]
---

# Configure a CNAME record on DNSPod

This topic describes how to configure a CNAME record on DNSPod. After you add a domain name for CDN, Alibaba Cloud CDN assigns a canonical domain name \(CNAME\) to the domain name for CDN. You must add a CNAME record to map the domain name for CDN to the canonical domain name. This ensures that Alibaba Cloud CDN can direct the requests that are destined for the domain name for CDN to Alibaba Cloud CDN nodes.

You have logged on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

1.  Obtain the CNAME assigned to the accelerated domain name.

    1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

    2.  In the left-side navigation pane, click **Domain Names**.

    3.  On the **Domain Names** page, copy the CNAME of the accelerated domain name.

        ![Click Domain Names](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3630062061/p66555.png)

2.  Add a CNAME record to DNSPod. To add a CNAME record, complete these steps:

    1.  Log on to the **DNS** console of DNSPod.

    2.  On the domain name resolution page for the target domain name, click **Add Record**.

    3.  Set the following parameters:

        -   Type: Select **CNAME**.
        -   Host: Enter the prefix of the domain name for CDN. For example, if your domain name for CDN is `testcdn.aliyun.com`, its prefix is `testcdn`.
        -   Value: Enter the CNAME domain name that you have obtained in step 1.
        -   ISP Line: Use the default value.
        -   TTL: Use the default value.
    4.  Click **Save**.

        The CNAME record is added. After the CNAME record takes effect, CDN acceleration is automatically enabled for the domain name.

        **Note:**

        -   After you add a CNAME record, it immediately takes effect. After you modify a CNAME record, the modifications take effect within 72 hours.
        -   After you add a CNAME record, it takes approximately 10 minutes for the system to update the status in the console. The system may prompt that you must add a CNAME record. Ignore the message.
3.  Check whether the CNAME record has taken effect.

    1.  Open the Command Prompt in Windows.

    2.  Use the Command Prompt to ping the accelerated domain name. If the CNAME in the output matches the CNAME assigned to the accelerated domain name in the Alibaba Cloud CDN console, it indicates that the CDN service is enabled for the domain name.

        ![Check whether the CNAME record has taken effect](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7423839951/p66693.png)


