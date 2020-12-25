---
keyword: [CNAME, add a CNAME record on HiChina, CNAME mapping on HiChina, CNAME of Alibaba Cloud domain name]
---

# Configure a CNAME record in Alibaba Cloud DNS

After you add a domain name to Alibaba Cloud Content Delivery Network \(CDN\), Alibaba Cloud CDN assigns a canonical name \(CNAME\) to the domain name. To enable the Alibaba Cloud CDN service for the domain name, you must add a CNAME record to map the domain name to the CNAME. This way, requests that are sent to the domain name can be redirected to CDN nodes. This topic describes how to configure a CNAME record for a domain name in the Alibaba Cloud DNS console.

1.  Obtain the CNAME that is assigned to the domain name.

    1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

    2.  In the left-side navigation pane, click **Domain Names**.

    3.  On the **Domain Names** page, copy the CNAME of the domain name.

        ![Domain Names](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3630062061/p66555.png)

2.  Add a CNAME record for the domain name.

    The following example shows how to add a CNAME record for a domain name. The Alibaba Cloud DNS console is used in this example. If your DNS service is provided by other DNS service providers, such as DNSPod, Xinnet, or GoDaddy, add a CNAME record for your domain name in the system of your service provider. The procedure is similar to the one that is described in this topic.

    1.  Log on to the [Alibaba Cloud DNS console](https://dc.console.aliyun.com/dns).

    2.  On the **Manage DNS** page, click the Domains tab, select the domain name that you want to manage, and then click **Configure** in the Actions column.

    3.  Click **Add Record** and add a CNAME record.

        **Note:** Each CNAME can be mapped to only one domain name to be accelerated. The CNAME of a top-level domain name cannot be mapped to its second-level domain names. If you want to accelerate a second-level domain name, add the domain name to Alibaba Cloud CDN. Alibaba Cloud then assigns a CNAME to the domain name. Alternatively, you can add a second-level wildcard domain name to Alibaba Cloud CDN. Domain names that match the wildcard domain name can be mapped to the CNAME of the wildcard domain name.

        ![Add a CNAME record](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7526528061/p64412.png)

        -   Type: Select `CNAME` from the drop-down list.
        -   Host: Enter the prefix of the domain name.

            |Domain name|Host|
            |:----------|:---|
            |`testcdn.aliyun.com`|`testcdn`|
            |`www.aliyun.com`|`www`|
            |`aliyun.com`|`@`|
            |`*.aliyun.com`|`*`|

        -   ISP Line: Use the default value.
        -   Value: Enter the CNAME that is assigned to the domain name.
        -   TTL: Use the default value.
    4.  Click **OK**.

        After the CNAME record takes effect, Alibaba Cloud CDN acceleration is automatically enabled for the domain name.

        **Note:**

        -   After you add a CNAME record, it immediately takes effect. After you modify a CNAME record, the modifications take effect within 72 hours.
        -   After you add a CNAME record, it takes about 10 minutes for the system to update the status in the console. The system may prompt that you must add a CNAME record. Ignore the message.
3.  Check whether the CNAME record has taken effect.

    1.  Open the Command Prompt in Windows.

    2.  Use the Command Prompt to ping the domain name. If the CNAME in the output matches the CNAME that is assigned to the domain name to be accelerated in the Alibaba Cloud CDN console, it indicates that Alibaba Cloud CDN acceleration is enabled for the domain name.

        ![Check whether the CNAME record has taken effect](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7423839951/p66693.png)


