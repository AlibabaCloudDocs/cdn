# Verify the ownership of a domain name

The first time a domain name is added to Alibaba Cloud Content Delivery Network \(CDN\), Alibaba Cloud CDN verifies the ownership of the domain name. If you pass the verification process, Alibaba Cloud CDN identifies you as the owner of the domain name. If you add the domain name to Alibaba Cloud CDN again or add its subdomain names to Alibaba Cloud CDN, the ownership verification process is not needed. You can use a Domain Name System \(DNS\) record or upload the verification file to prove the ownership. In the following example, `a.com` is used to demonstrate how to prove the ownership of a domain name.

## Method 1: Use a DNS record to prove the ownership

The first time a domain name is added to Alibaba Cloud CDN, you can add a DNS record to prove that you own the domain name.

1.  Obtain the record type, hostname, and record value.

    1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

    2.  In the left-side navigation pane, choose **Domain Names** \> **Add Domain Name**. The first time a domain name is added to Alibaba Cloud CDN, you can follow the instructions on the page to add a TXT record.

        **Note:** The [DescribeVerifyContent](https://www.alibabacloud.com/help/doc-detail/176905.htm) operation can be used to generate the record value. The [AddCdnDomain](https://www.alibabacloud.com/help/doc-detail/91176.htm) and [BatchAddCdnDomain](https://www.alibabacloud.com/help/doc-detail/124881.htm) operations can be used to add one or more domain names to Alibaba Cloud CDN. To add a domain name by calling API operations, call the [DescribeVerifyContent](https://www.alibabacloud.com/help/doc-detail/176905.htm) operation to obtain the record value and perform the following steps to add a TXT record. Then, you can call the [AddCdnDomain](https://www.alibabacloud.com/help/doc-detail/91176.htm) or [BatchAddCdnDomain](https://www.alibabacloud.com/help/doc-detail/124881.htm) operation to add one or more domain names to Alibaba Cloud CDN.

2.  Add a DNS record.

    1.  Log on to the [Alibaba Cloud DNS console](https://dc.console.aliyun.com/dns).

        In this example, Alibaba Cloud DNS is used to add a DNS record. You can add a DNS record through other service providers such as DNSPod and Xinnet in a similar way.

    2.  On the **Manage DNS** page, find the domain name `a.com` and click **Configure** in the Actions column.

    3.  Click **Add Record**. Enter the record type, hostname, and record value that you have obtained in Step 1.

3.  Complete the verification process.

    1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

    2.  Click **Verify** to complete the verification process.


## Method 2: Upload a verification file to prove the ownership

The first time a domain name is added to Alibaba Cloud CDN, you can upload a verification file to prove that you own the domain name.

1.  2.  In the left-side navigation pane, choose **Domain Names** \> **Add Domain Name** \> **Method 2: Verification File**.

3.  Download the `verification.html` verification file.

    **Note:** The [DescribeVerifyContent](https://www.alibabacloud.com/help/doc-detail/176905.htm) operation can be used to generate verification strings. The [AddCdnDomain](https://www.alibabacloud.com/help/doc-detail/91176.htm) and [BatchAddCdnDomain](https://www.alibabacloud.com/help/doc-detail/124881.htm) operations can be used to add one or more domain names to Alibaba Cloud CDN. To add a domain name by calling API operations, call the [DescribeVerifyContent](https://www.alibabacloud.com/help/doc-detail/176905.htm) operation to obtain the verification strings. Then, enter the verification strings in the `verification.html` file and perform the following steps to upload the file.

4.  Upload the verification file to the root directory of the origin server of your domain name. The origin server can be an Elastic Compute Service \(ECS\) instance, an Object Storage Service \(OSS\) bucket, a Cloud Virtual Machine \(CVM\) instance, a Container-Optimized OS \(COS\) instance, or an Elastic Compute Cloud \(EC2\) instance.

    Alibaba Cloud CDN will visit the origin server at `http://a.com/verification.html` to obtain the verification file and determine whether you have uploaded the verification file as required. Make sure that the file is accessible.

5.  Click **Verify** to complete the verification process.


## FAQ

The following issues may occur when you add a new domain name to Alibaba Cloud CDN.

-   Q: Why does Alibaba Cloud CDN verify the ownership of domain names?

    A: The ownership verification process is required to ensure that the domain name is added by its owner. If a domain name of User A is added to Alibaba Cloud CDN by User B, conflicts and security risks may occur.

-   Q: I have multiple Alibaba Cloud accounts. If this is the first a domain name is added to Alibaba Cloud under these accounts, do I need to pass the ownership verification process for each account?

    A: Yes. Each Alibaba Cloud account is recognized as an independent user. The first time a domain name is added to Alibaba Cloud CDN, the user \(account\) must pass the ownership verification process.

-   Q: After I pass the ownership verification process by adding a DNS record or uploading a verification file, can I delete the record or file?

    A: Yes. The required DNS record or file is only used for ownership verification. After you pass the verification process, you can delete the record or file.

-   Q: Do I need to prove the ownership of a domain name that has been added to Alibaba Cloud CDN?

    A: No. For example, you have added the domain name b.a.com to Alibaba Cloud CDN and the Canonical Name \(CNAME\) that is assigned to the domain name works as expected. In this case, you are deemed to own the domain name a.com. When you add subdomain names of a.com, such as xx.a.com or xxx.a.com, you do not need to pass the ownership verification process.

-   Q: Do I need to prove the ownership of a domain name if I call the AddDomain operation to add the domain name to Alibaba Cloud CDN?

    A: Yes. The method to prove the ownership of the domain name is similar to those added to Alibaba Cloud CDN through the console. You can add a DNS record or upload the required verification file to the root directory of the origin server of your domain name. Then, call the AddDomain operation to add the domain name to Alibaba Cloud CDN.

-   Q: What can I do if I cannot prove the ownership of my domain name by adding a DNS record or uploading a verification file to the origin server?

    A: To address this issue, you can [submit a ticket](https://workorder-intl.console.aliyun.com/#/ticket/createIndex). In the ticket, state the reason why you cannot prove the ownership through the given methods, and include the information that can be used to prove your identity as the domain owner. Alibaba Cloud will conduct manual verification.


