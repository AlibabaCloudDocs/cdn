# Configure a CNAME on Alibaba Cloud \(HiCloud\) {#task_187531 .task}

This topic describes how to configure a Canonical Name \(CNAME\). After you add a domain, Alibaba Cloud CDN assigns a CNAME address to the domain. You need to point the domain to its CNAME address so that CDN can direct the requests destined for the domain to CDN nodes.

1.  Obtain the CNAME of the target domain name by completing the following steps: 
    1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).
    2.  Navigate to the Domain Names page, find the target domain name and in the **CNAME** column copy the CNAME. 

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5113/156440903245282_en-US.png)

2.  Add a CNAME record to the DNS by completing the following steps: 
    1.  Log on to the [Alibaba Cloud DNS console](https://dc.console.aliyun.com/dns/?spm=5176.200001.0.0.pbY4Je).
    2.  On the Manage DNS page, click the **Domains** tab, find the target domain name, and in the **Actions** column click **Configure**. 

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5113/156440903245284_en-US.png)

    3.  Click **Add Record**. 

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5113/156440903245285_en-US.png)

    4.  In the Add Record dialog box, set the parameters and click **OK**. 

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5113/156440903350722_en-US.png)

        -   **Type**: Select **CNAME**.
        -   **Host**: Enter the prefix of the domain name.

            |If the domain name is...|Then the host is...|
            |:-----------------------|:------------------|
            |`testcdn.aliyun.com`|`testcdn`|
            |`www.aliyun.com`|`www`|
            |`aliyun.com`|`@`|
            |`*.aliyun.com`|`*`|

        -   **ISP Line**: Retain the default value.
        -   **Value**: Enter the CNAME obtained in Step 1.
        -   **TTL**: Retain the default value.
        The CDN service takes effect immediately after the new CNAME record takes effect.

        **Note:** 

        -   A new CNAME record takes effect immediately, but a modified CNAME record takes effect within 72 hours.
        -   After you add a CNAME record, it takes about 10 minutes to update the status of the corresponding domain name.
3.  Verify that the new CNAME record takes effect. 

    The time when a new CNAME record takes effect varies depending on the DNS provider.

    You can run the ping or dig command to check whether the target domain is accessible. If the access request is directed to `*.*kunlun*.com`, the CNAME record and CDN service both take effect.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5113/156440903345287_en-US.png)


