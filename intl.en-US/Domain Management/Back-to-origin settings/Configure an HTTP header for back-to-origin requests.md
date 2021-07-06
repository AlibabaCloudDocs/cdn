---
keyword: [HTTP header for back-to-origin requests, back-to-origin]
---

# Configure an HTTP header for back-to-origin requests

HTTP headers define the required resources, the behavior of clients or servers that process the messages, and the parameters of an HTTP transaction. If the back-to-origin process requires HTTP headers to implement relevant logic, you can configure HTTP headers for back-to-origin requests. This topic describes how to add, modify, and delete an HTTP request header.

HTTP headers are components of the header section of request and response messages that are transmitted over HTTP. HTTP headers include general headers, request headers, and response headers.

![HTTP request headers](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3574297061/p87913.png)

**Note:** Alibaba Cloud CDN provides a new feature that allows you to configure HTTP request headers. For more information, see [Customize an HTTP request header](/intl.en-US/Domain Management/Back-to-origin settings/Customize an HTTP request header.md).

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the management pane of the domain name, click **Back-to-origin**.

5.  Click the **Custom Request Header** tab.

6.  Click **Customize**.

7.  In the **Custom Request Header** dialog box, select **Custom Origin Header** from the Parameter drop-down list, and set **Custom Parameters** and **Value**.

    **Note:** When you set **Custom Request Header**, we recommend that you set **Parameter** to **Custom Origin Header** and create an HTTP header based on your business requirements.

    ![Customize an HTTP header](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/601148/156726429749739_en-US.png)

    If you want to modify or delete an HTTP header, click **Modify** or **Delete** in the Actions column.

8.  Click **OK**.


## What to do next

When you customize an HTTP header in the **Custom Request Header** dialog box, if you select **Parameter** from the **Parameter** drop-down list to add a custom header, the error message may appear. This indicates that the specified header field is a reserved field for internal use. Use another header field.

**Related topics**  


[BatchSetCdnDomainConfig](/intl.en-US/New API Reference/Domain name management/BatchSetCdnDomainConfig.md)

