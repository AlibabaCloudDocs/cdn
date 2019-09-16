# Implement acceleration from the OSS console {#task_828194 .task}

This topic describes how to implement CDN acceleration for the access to OSS buckets from the OSS console.

1.  Log on to the [OSS console](https://oss.console.aliyun.com/overview).
2.  In the left-side **Storage Space** list, click the name of the target bucket. 

    ![OSS console](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/669803/156860459250559_en-US.png)

3.  Choose **Domain Names** \> **Bind Custom Domain Name**. The Bind Custom Domain Name dialog box appears. 

    ![Bind Custom Domain Name dialog box](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/615645/156860459449828_en-US.png)

4.  Configure the information of the custom domain to be bound. 

    |Parameter|Description|
    |---------|-----------|
    |Custom Domain Name|Enter the custom domain name, for example, hello-world.com.|
    |Alibaba Cloud CDN|Turn on Alibaba Cloud CDN.|
    |Add CNAME Record Automatically|If the domain to be bound is managed by the current Alibaba Cloud account, you can enable this function to automatically add a CNAME record for the domain. If the domain name is not under this account, you must manually add the CNAME record at your DNS service provider. For more information, see [Configure a CNAME record on Alibaba Cloud DNS \(HiChina\)](../reseller.en-US/Quick Start/Configure a CNAME record/Configure a CNAME record on Alibaba Cloud DNS (HiChina).md#), [Configure a CNAME on Tencent Cloud \(DNSPod\)](../reseller.en-US/Quick Start/Configure a CNAME record/[DO NOT TRANSLATE].md#), or [Configure a CNAME on Xinnet](../reseller.en-US/Quick Start/Configure a CNAME record/[DO NOT TRANSLATE].md#).|

5.  Click **Submit**. 

    **Note:** 

    -   A domain name conflict indicates that the domain name has been bound to another bucket. You can click to obtain the TXT information at the prompt and verify the ownership of the domain by adding a TXT record to forcibly bind the domain to this bucket. This operation unbinds the domain from the previous bucket.
6.  After you update the domain name information, click **Manage Binding Configurations** to view the **Alibaba Cloud CDN domain name** and the **bucket domain name**. 

    **Note:** It takes about 1 minute to update the domain name information.


