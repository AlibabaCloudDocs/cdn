# Add a CDN domain {#task_678836 .task}

If you want to use CDN to accelerate business on a specific website, you need to use the website as the origin site to add a CDN domain for it. CDN caches resources on the origin site to the CDN acceleration node through the CDN domain to accelerate resource access. This topic describes how to add a CDN domain.

1.  Log on to the [Alibaba Cloud CDN console](https://partners-intl.aliyun.com/login-required#cdn).
2.  In the left-side navigation pane, click **Domain Names**.
3.  On the Domain Names page, click **Add Domain Name**. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/545079/156654189957076_en-US.png)

4.  Configure the following parameters: **Domain Name**, **Resource Group**, **Business Type**, **Origin Info**, and **Region**. 

    Parameters on the Add Domain Name page are described as follows.

    |Parameter|Option|Description|
    |---------|------|-----------|
    |Domain Name|N/A| Enter a domain name, for example, ch.aliyun.com. Follow these restrictions and guidelines:

    -   Generally, a subdomain name or a wildcard domain name is used as the CDN domain name, for example, `cdntest.example.com`.
    -   A CDN domain cannot be added multiple times. If a **DomainAlreadyExist** error occurs, submit a ticket.
    -   Up to 50 CDN domains can be added under each account. To add more CDN domains, submit a ticket.
    -   The content in the domain must comply with CDN specifications. For more information, see [Limits](../reseller.en-US/Product Introduction/Limits on domains.md#).
 |
    |Business Type|[Images and small files](../reseller.en-US/Product Introduction/Scenarios/Images and small files.md#)|If you want to accelerate the small-sized static content on your website, such as small files, images, and style sheets, we recommend that you select the **Image and Small File** type.|
    |[Large file download](../reseller.en-US/Product Introduction/Scenarios/Large file download.md#)|If you want to accelerate large files \(static files larger than 20 MB\), such as game installation package, app update, mobile ROM upgrade, and app package download, we recommend that you select the **Large File Download** type.|
    |[VOD](../reseller.en-US/Product Introduction/Scenarios/VOD.md#)|If you want to accelerate on-demand video or audio content, we recommend that you select the **VOD** type.|
    |[Live Streaming](../reseller.en-US/Product Introduction/Scenarios/Live Streaming.md#)|If you want to accelerate live streaming content, we recommend that you select the **Live Streaming** type. Follow these restrictions and guidelines:     -   Only streams in RTMP or HLS format are supported.
    -   Custom origins are not supported. CDN provides a unified live center server: `video-center.alivecdn.com`.
 |
    |Type|IP|You can specify the public IP addresses of multiple servers. IP addresses of Alibaba Cloud ECS instances are exempt from manual review.|
    |Origin Domain|You can specify the domain names of multiple origin servers. **Note:** The origin domain you specified cannot be the same as the CDN domain. Otherwise, a DNS resolution loop will occur, and the origin requests cannot be forwarded correctly. For example, if you set the CDN domain name to cdn.yourdomain.com, you can set the origin domain to img.yourdomain.com.

 |
    |OSS Domain|You can manually enter the Internet domain name of an Alibaba Cloud OSS bucket, such as xxx.oss-cn-hangzhou.aliyuncs.com. To view the Internet domain name of the OSS bucket, go to the OSS console. You can also directly select an OSS bucket under the same account.|
    |FC Domain|You must specify the Region and Domain Name of Function Compute.|
    |Region|All Regions Excluding Mainland China|If you select this option, no ICP filing is required.|
    |All Regions Including Mainland China|If you select this option, you must apply for an ICP license with the Ministry of Industry and Information Technology \(MIIT\). For more information, see [Domain filing](../reseller.en-US/Product Introduction/Limits on domains.md#section_r1h_lgx_wdb).|
    |Mainland China|If you select this option, you must apply for an ICP license with the Ministry of Industry and Information Technology \(MIIT\). For more information, see [Domain filing](../reseller.en-US/Product Introduction/Limits on domains.md#section_r1h_lgx_wdb).|

5.  Click **Next**. 

    After your CDN domain is reviewed and approved, you can view the domain name on the **Domain Names** page. If the domain is added, its state is displayed as **Enabled**.

    **Note:** 

    -   If you want to speed up the review process, submit a ticket.
    -   If your origin is in Alibaba Cloud ECS or OSS, the review takes less time to complete.
    -   After the CDN domain is added, Alibaba Cloud CDN assigns the CDN domain the corresponding CNAME address. The CDN service takes effect for the domain only after you add the corresponding CNAME record.

