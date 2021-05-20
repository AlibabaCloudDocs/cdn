# Configure Alibaba Cloud CDN in accelerated regions outside mainland China in the CDN console

This topic describes how to configure Alibaba Cloud Content Delivery Network \(CDN\) in accelerated regions outside mainland China in the Alibaba Cloud CDN console. To accelerate content delivery in Hong Kong, Macao, Taiwan, and other regions outside mainland China, follow the procedure described in this topic to activate and configure Alibaba Cloud CDN.

An [Alibaba Cloud account](https://account.alibabacloud.com/register/intl_register.htm) is created and [real-name verification](https://www.alibabacloud.com/help/doc-detail/52595.htm) is completed.

Alibaba Cloud CDN applies to a wide array of scenarios, including but not limited to:

-   Small image files: Your websites or applications offer downloads of images and small files in formats such as HTML, CSS, and JavaScript.
-   Large files: Your websites or applications offer downloads of files larger than 20 MB, such as game applications, client applications, and mobile apps.
-   On-demand audio and video streaming: Your websites or applications offer on-demand video streaming or short video streaming. Mainstream media formats such as MP4 and FLV are supported.

If your workloads are deployed in one of the preceding scenarios, and the origin server is deployed in a region outside mainland China, perform the following steps to configure Alibaba Cloud CDN:

## Step 1: Activate Alibaba Cloud CDN

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com/overview) to activate Alibaba Cloud CDN.

2.  On the **Alibaba Cloud CDN** page, select a **Billing Method**.

    For more information about the pricing of Alibaba Cloud CDN, see [Billing rules](/intl.en-US/Acceleration in Hong Kong (China), Macao (China), Taiwan (China), and regions outside China/Billing rules/Overview.md).

3.  Select **I agree with Alibaba Cloud CDN Agreement of Service** and click **Enable Now**.


## Step 2: Add the domain name to be accelerated

1.  In the left-side navigation pane, click **Domain Names**.

2.  On the **Domain Names** page, click **Add Domain Name**.

3.  Set the following parameters: **Domain Name to Accelerate**, **Resource Groups**, **Business Type**, **Port**, and **Region**.

    **Note:** To accelerate content delivery in Hong Kong, Macao, Taiwan, and other regions outside mainland China, select Global or Global \(Excluding Mainland China\). If you select Global as the accelerated region, the accelerated domain name must obtain an Internet Content Provider \(ICP\) number.We recommend that you apply for an ICP number through Alibaba Cloud ICP Filing System.

    |Parameter|Value|Description|
    |---------|-----|-----------|
    |**Domain Name to Accelerate**|-|Enter the domain name that you want to add to Alibaba Cloud CDN, for example, ch.aliyun.com. Note that:

    -   You can use a subdomain name or a wildcard domain name as the accelerated domain name, for example, `cdntest.example.com`.
    -   You cannot add a duplicate domain name to Alibaba Cloud CDN. If a **DomainAlreadyExist** error occurs, [submit a ticket](https://selfservice.console.aliyun.com/ticket/createIndex).
    -   You can add at most 50 domain names to Alibaba Cloud CDN under each Alibaba Cloud account. To add more domain names, [submit a ticket](https://selfservice.console.aliyun.com/ticket/createIndex).
    -   Content that is delivered from your domain name must comply with the limits of Alibaba Cloud CDN and the relevant regulations. For more information, see [Limits](/intl.en-US/Product Introduction/Limits.md). |
    |**Business Type**|[Image and Small File](/intl.en-US/Product Introduction/Scenarios/Image and small file distribution.md)|If you want to accelerate the delivery of small-sized static content on your website, we recommend that you select **Image and Small File** from the Business Type drop-down list. Examples of small-sized static content include small-sized files, images, and style sheets.|
    |[Delivery of large files](/intl.en-US/Product Introduction/Scenarios/Delivery of large files.md)|If you want to accelerate the delivery of static files larger than 20 MB, we recommend that you select **Large File Download** from the Business Type drop-down list. Examples of large-sized static files include game installation packages, app update packages, mobile read-only memory \(ROM\) upgrade packages, and app packages.|
    |[VOD](/intl.en-US/Product Introduction/Scenarios/ApsaraVideo for VOD.md)|If you want to accelerate the delivery of on-demand video or audio content, we recommend that you select **VOD** from the Business Type drop-down list.|
    |**Origin Info**|**IP**|You can enter the public IP addresses of one or more servers. IP addresses of Alibaba Cloud Elastic Compute Service \(ECS\) instances do not need to be reviewed.|
    |**Site Domain**|You can enter the domain names of one or more origin servers. **Note:** The domain name of the origin server that you specified cannot be the same as the accelerated domain name. Otherwise, a DNS resolution loop occurs and requests cannot be redirected to the origin server correctly. For example, if the domain name of your origin server is img.yourdomain.com, you can set the accelerated domain name to cdn.yourdomain.com. |
    |**OSS Domain**|You can enter the public endpoint of an Alibaba Cloud Object Storage Service \(OSS\) bucket, for example, xxx.oss-cn-hangzhou.aliyuncs.com. To view the public endpoint of an OSS bucket, go to the OSS console. You can also select the endpoint of an OSS bucket under the current Alibaba Cloud account from the Domain Name drop-down list.|
    |**Function Compute Domain**|If you select this value, you must set the Region and Domain Name parameters.|
    |**Port**|-|Select a port based on your business requirements.

    -   Port 80

Data is transmitted over HTTP.

    -   Port 443

Data is transmitted over HTTPS. |
    |**Region**|**Global \(Excluding Mainland China\)**|If you select **Global \(Excluding Mainland China\)**, you do not need to obtain an ICP number for the domain name.|
    |**Global**|If you select **Global**, you must obtain an ICP number for the domain name. For more information, see [Apply for an Internet Content Provider \(ICP\) number for an accelerated domain name](/intl.en-US/Product Introduction/Limits.md).|
    |**Mainland China Only**|If you select **Mainland China Only**, you must obtain an ICP number for the domain name. For more information, see [Apply for an Internet Content Provider \(ICP\) number for an accelerated domain name](/intl.en-US/Product Introduction/Limits.md).|

4.  Click **Next**.


## Step 3: Configure a CNAME record

After you add a domain name to Alibaba Cloud CDN, Alibaba Cloud CDN verifies the ownership of the domain name. After the domain name passes the ownership verification, Alibaba Cloud CDN assigns a Canonical Name \(CNAME\) to the domain name. To enable CDN acceleration for the domain name, you must add a CNAME record to map the domain name to the CNAME. This way, requests sent to the domain name can be redirected to CDN nodes. The following example demonstrates how to add a CNAME record for the domain name. Alibaba Cloud DNS \(previously known as HiChina\) is used in the example.

1.  Obtain the CNAME assigned to the domain name.

    1.  In the left-side navigation pane, click **Domain Names**.

    2.  On the **Domain Names** page, copy the CNAME of the accelerated domain name.

2.  Add a CNAME record.

    1.  Log on to the [Alibaba Cloud DNS console](https://dc.console.aliyun.com/dns/).

    2.  On the **Manage DNS** page, click the Domains tab, select the domain name that you want to manage, and then click **Configure** in the Actions column.

    3.  Click **Add Record** and add a CNAME record.

    4.  Click **OK**.

        The CNAME record is added. CDN acceleration is automatically enabled for the domain name immediately after the CNAME record takes effect. After you add a CNAME record, it immediately takes effect. After you modify a CNAME record, the modifications take effect within 72 hours.

3.  Check whether the CNAME record has taken effect.

    1.  Open the Command Prompt in Windows.

    2.  Enter ping or dig and the accelerated domain name into the Command Prompt.

        If the output includes `*.*kunlun*.com`, both the CNAME record and CDN acceleration have taken effect.

        ![Ping the accelerated domain name](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7423839951/p66693.png)


