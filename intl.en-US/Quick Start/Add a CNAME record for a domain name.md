---
keyword: [CNAME, HiChina CNAME record for CDN, HiChina CNAME record, Domains CNAME]
---

# Add a CNAME record for a domain name

After you add a domain name to Alibaba Cloud Content Delivery Network \(CDN\), the system assigns a Canonical Name \(CNAME\) to the domain name. You must add a CNAME record to map the domain name to the CNAME. This way, requests that are destined for the domain name are redirected to CDN nodes to accelerate content delivery. If an A record conflicts with the CNAME record that you want to use, change the A record to a CNAME record.

## Methods for adding a CNAME record

You must add CNAME records in the system of your DNS service provider. This topic describes how to add a CNAME record on Alibaba Cloud, Tencent Cloud, or Xinnet. Other DNS service providers adopt similar methods.

-   For more information about how to add a CNAME record on Alibaba Cloud, see [Add a CNAME record on Alibaba Cloud](#section_pbv_cbm_ipp).
-   For more information about how to add a CNAME record on Tencent Cloud, see [Add a CNAME record on Tencent Cloud](#section_1bd_hlb_5w4).
-   For more information about how to add a CNAME record on Xinnet, see [Add a CNAME record on Xinnet](#section_z5s_mcc_0cq).

## Add a CNAME record on Alibaba Cloud

If your DNS service provider is Alibaba Cloud, perform the following steps to add a CNAME record for the domain name:

1.  Obtain the CNAME that is assigned to the domain name.

    1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

    2.  In the left-side navigation pane, click **Domain Names**.

    3.  On the **Domain Names** page, copy the CNAME of the domain name.

        ![Domain Names](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8550435161/p66555.png)

2.  Add a CNAME record for the domain name.

    1.  Log on to the [Alibaba Cloud DNS console](https://dns.console.aliyun.com).

    2.  On the **Manage DNS** page, find the domain name that you want to manage and click **Configure** in the Actions column.

    3.  Click **Add Record** and add a CNAME record.

        **Note:**

        -   The CNAME record of a specific domain name takes precedence over that of a wildcard domain name. If the domain name to accelerate is a wildcard domain name, and the host record includes an asterisk \(\*\), you must delete all effective DNS records of the second-level domain names that match the wildcard domain name.
        -   If the CNAME record that you want to use conflicts with an existing DNS record, we recommend that you use another domain name or modify the DNS records.
        ![Add a CNAME record](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7526528061/p64412.png)

        |Parameter|Description|Example|
        |---------|-----------|-------|
        |**Type**|Select CNAME from the drop-down list.|CNAME|
        |**Host**|Enter the prefix of the domain name.|        -   If the domain name to accelerate is `testcdn.aliyun.com`, enter `testcdn`.
        -   If the domain name to accelerate is `www.aliyun.com`, enter `www`.
        -   If the domain name to accelerate is `aliyun.com`, enter `@`.
        -   If the domain name to accelerate is `*.aliyun.com`, enter `*`. |
        |**ISP Line**|Enter the default Internet service provider \(ISP\) line.|Keep the default setting.|
        |**Value**|Enter the CNAME of the domain name.

**Note:** Each accelerated domain name is assigned a unique CNAME. Second-level domain names cannot use the CNAME of the top-level domain name. If you need to accelerate a second-level domain name, add the second-level domain name to Alibaba Cloud CDN. Alibaba Cloud then assigns a CNAME to the second-level domain name. Alternatively, you can add a second-level wildcard domain name to Alibaba Cloud CDN. Domain names that match the wildcard domain name can be mapped to the CNAME of the wildcard domain name. For more information, see [Add a domain name to Alibaba Cloud CDN](/intl.en-US/Quick Start/Add a domain name to Alibaba Cloud CDN.md).

|all.example.com.w.kunlunsl.com|
        |**TTL**|Enter a TTL value for the CNAME record. A smaller value indicates a shorter time to apply record updates. The default TTL value is 10 minutes.|Keep the default setting.|

    4.  Click **OK**.

        After the CNAME record takes effect, acceleration is immediately enabled for the domain name. After you add a CNAME record, it immediately takes effect. After you modify a CNAME record, the modifications take effect within 72 hours. After you add a CNAME record, it takes about 10 minutes for the system to update the status in the console. The system may prompt that you must add a CNAME record. Ignore the message.

3.  Check whether the CNAME record takes effect.

    1.  Open Command Prompt in Windows.

    2.  Run the ping command to ping the domain name. If the CNAME in the output is the same as the CNAME that is assigned to the domain name, it indicates that acceleration is enabled for the domain name.

        ![Check whether the CNAME record takes effect](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7423839951/p66693.png)


## Add a CNAME record on Tencent Cloud

If your DNS service provider is Tencent Cloud, perform the following steps to add a CNAME record for the domain name:

1.  Obtain the CNAME that is assigned to the domain name.

    1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

    2.  In the left-side navigation pane, click **Domain Names**.

    3.  On the **Domain Names** page, copy the CNAME of the domain name.

        ![Domain Names](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8550435161/p66555.png)

2.  Add a CNAME record for the domain name.

    1.  Log on to the DNSPod console.

    2.  On the DNSPod page, click **Add Records** and add a CNAME record.

        |Parameter|Description|Example|
        |---------|-----------|-------|
        |**Host**|Enter the prefix of the domain name.|        -   If the domain name to accelerate is `testcdn.aliyun.com`, enter `testcdn`.
        -   If the domain name to accelerate is `www.aliyun.com`, enter `www`.
        -   If the domain name to accelerate is `aliyun.com`, enter `@`.
        -   If the domain name to accelerate is `*.aliyun.com`, enter `*`. |
        |**Type**|Select CNAME from the drop-down list.|CNAME|
        |**Split Zone**|Select Default from the drop-down list.|Keep the default setting.|
        |**Value**|Enter the CNAME of the domain name.

**Note:** Each accelerated domain name is assigned a unique CNAME. Second-level domain names cannot use the CNAME of the top-level domain name. If you need to accelerate a second-level domain name, add the second-level domain name to Alibaba Cloud CDN. Alibaba Cloud then assigns a CNAME to the second-level domain name. Alternatively, you can add a second-level wildcard domain name to Alibaba Cloud CDN. Domain names that match the wildcard domain name can be mapped to the CNAME of the wildcard domain name. For more information, see [Add a domain name to Alibaba Cloud CDN](/intl.en-US/Quick Start/Add a domain name to Alibaba Cloud CDN.md).

|all.example.com.w.kunlunsl.com|
        |**Weight**|You do not need to specify this parameter.|N/A|
        |**MX**|You do not need to specify this parameter.|N/A|
        |**TTL**|Enter a TTL value for the CNAME record. A smaller value indicates a shorter time to apply record updates.|Keep the default setting.|

    3.  Click **Confirm**.

        After the CNAME record takes effect, acceleration is immediately enabled for the domain name. After you add a CNAME record, it takes about 10 minutes for the system to update the status in the console. The system may prompt that you must add a CNAME record. Ignore the message.

3.  Check whether the CNAME record takes effect.

    1.  Open Command Prompt in Windows.

    2.  Run the ping command to ping the domain name. If the CNAME in the output is the same as the CNAME that is assigned to the domain name, it indicates that acceleration is enabled for the domain name.

        ![Check whether the CNAME record takes effect](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7423839951/p66693.png)


## Add a CNAME record on Xinnet

If your DNS service provider is Xinnet, perform the following steps to add a CNAME record for the domain name:

1.  Obtain the CNAME that is assigned to the domain name.

    1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

    2.  In the left-side navigation pane, click **Domain Names**.

    3.  On the **Domain Names** page, copy the CNAME of the domain name.

        ![Domain Names](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8550435161/p66555.png)

2.  Add a CNAME record for the domain name.

    1.  Log on to Xinnet.

    2.  Navigate to the DNS records page and find the domain name that you want to manage. Click **Add CNAME Record** and add a CNAME record.

        |Parameter|Description|Example|
        |---------|-----------|-------|
        |**CNAME**|Enter the CNAME assigned to the domain name. **Note:** Each accelerated domain name is assigned a unique CNAME. Second-level domain names cannot use the CNAME of the top-level domain name. If you need to accelerate a second-level domain name, add the second-level domain name to Alibaba Cloud CDN. Alibaba Cloud then assigns a CNAME to the second-level domain name. Alternatively, you can add a second-level wildcard domain name to Alibaba Cloud CDN. Domain names that match the wildcard domain name can be mapped to the CNAME of the wildcard domain name. For more information, see [Add a domain name to Alibaba Cloud CDN](/intl.en-US/Quick Start/Add a domain name to Alibaba Cloud CDN.md).

|all.example.com.w.kunlunsl.com|
        |**Points To**|Enter the prefix of the domain name.|        -   If the domain name to accelerate is `testcdn.aliyun.com`, enter `testcdn`.
        -   If the domain name to accelerate is `www.aliyun.com`, enter `www`.
        -   If the domain name to accelerate is `aliyun.com`, enter `@`.
        -   If the domain name to accelerate is `*.aliyun.com`, enter `*`. |
        |**TTL**|Enter a TTL value for the CNAME record. A smaller value indicates a shorter time to apply record updates.|Keep the default setting.|

    3.  Click **Submit**.

        After the CNAME record takes effect, acceleration is immediately enabled for the domain name. After you add a CNAME record, it takes about 10 minutes for the system to update the status in the console. The system may prompt that you must add a CNAME record. Ignore the message.

3.  Check whether the CNAME record takes effect.

    1.  Open Command Prompt in Windows.

    2.  Run the ping command to ping the domain name. If the CNAME in the output is the same as the CNAME that is assigned to the domain name, it indicates that acceleration is enabled for the domain name.

        ![Check whether the CNAME record takes effect](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7423839951/p66693.png)


## What to do next

-   Create a cache expiration rule. The default TTL value of cached resources is 3,600 seconds. You can specify a TTL value based on your business requirements. The amount of back-to-origin network traffic and fees vary based on the TTL value. We recommend that you set a TTL value based on your business requirements. A small TTL value may cause CDN nodes to frequently redirect requests to the origin server and increase the amount of data transfer on the origin server. For more information, see [Create a cache expiration rule](/intl.en-US/Domain Management/Cache settings/Create a cache expiration rule.md).
-   Increase the cache hit ratio. If the cache hit ratio is lower than expected after you use Alibaba Cloud CDN to accelerate content delivery for the domain name, you can configure and enable the prefetch feature. This feature can prefetch content from the origin server to CDN nodes during off-peak hours. For more information, see [Configure the refresh and prefetch features](/intl.en-US/Service Management/Refresh and prefetch/Configure the refresh and prefetch features.md).

