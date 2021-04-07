---
keyword: [custom error page, pages for HTTP status codes, CDN]
---

# Create a custom error page

If the URL that a client wants to access does not exist, the server returns the HTTP 404 status code to the client. Alibaba Cloud Content Delivery Network \(CDN\) allows you to customize an error page that is returned to clients. This topic describes how to create a custom error page.

Alibaba Cloud provides a default error page and also supports custom error pages. In the following example, the 404 Not Found page is used to demonstrate the differences between a default error page and a custom error page.

-   Default page: When a response includes the HTTP 404 status code, the server returns the default 404 Not Found page.
-   Custom page: When a response includes the HTTP 404 status code, the server returns the custom page. You must specify the complete URL of the custom page.

**Note:**

-   Custom pages are classified as user resources. You are charged for custom pages based on the billing rules of Alibaba Cloud CDN.
-   For more information about 404 Not Found pages, see [Why does the 404 Not Found page appear?]()

## Scenarios

If a client requests a web service by using a browser and the requested URL does not exist, the website server returns the default 404 Not Found page. If you want to use a more friendly error page, you can create a custom error page and specify the complete URL of the page. Requests are redirected to the specified URL based on the HTTP status code in the responses.

## Procedure

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the management pane of the domain name, click **Cache**.

5.  Click the **Custom Pages** tab.

6.  Click **Customize**. In the dialog box that appears, select an HTTP status code and enter a URL.

    The HTTP 404 status code is used in this example. The 404 Not Found page `error404.html` and other static files are stored on the origin server. The accelerated domain name for the origin server is `exp.aliyun.com`. In this case, you can select the HTTP 404 HTTP status code and enter the complete URL of the custom page that belongs to the accelerated domain name. The complete URL is `http://exp.aliyun.com/error404.html` in this example.

    ![The Customize Page dialog box](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3826297061/p7276.png)

7.  Click **OK**.

    After the custom page is created, it is displayed on the **Custom Pages** tab. You can **Modify** or **Delete** the page.


## Related API operations

[BatchSetCdnDomainConfig](/intl.en-US/New API Reference/Domain name management/BatchSetCdnDomainConfig.md)

