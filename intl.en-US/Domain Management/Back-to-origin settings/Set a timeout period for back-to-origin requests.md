# Set a timeout period for back-to-origin requests

If a client requests content that is not cached on Alibaba Cloud Content Delivery Network \(CDN\) nodes, the CDN nodes retrieve the requested content from the origin server. You can set a timeout period for back-to-origin requests. The timeout period specifies the amount of time that a CDN node waits for a response after a request is redirected to the origin server. The default timeout period is 30 seconds. If the CDN node does not receive a response within the specified timeout period, the CDN node disconnects from the origin server. This topic describes how to set a timeout period for back-to-origin requests.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the management pane of the domain name, click **Back-to-origin**.

5.  In the **Back-to-origin Request Timeout** section, click **Modify**.

6.  In the **Back-to-origin Request Timeout** dialog box, set Timeout Value.

    ![Set a timeout period for back-to-origin requests](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6846219951/p51614.png)

7.  Click **OK**.


**Related topics**  


[BatchSetCdnDomainConfig](/intl.en-US/New API Reference/Domain name management/BatchSetCdnDomainConfig.md)

