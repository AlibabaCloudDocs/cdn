---
keyword: [customize an error page, set the status code page, CDN]
---

# Customize an error page

When a client requests a web service by using a browser, if the requested URL does not exist, the website hosting server returns the default 404 Not Found page. To improve the default error page of a web server and overall user experience, you can associate full URLs with error codes that are included in HTTP or HTTPS responses. When an error occurs, the server returns the associated custom page. This topic describes how to customize an error page.

Alibaba Cloud Content Delivery Network \(CDN\) provides two types of error pages for the status codes: default page and custom page. The status code 404 is used as an example to describe the differences between a default page and a custom page.

-   Default page: When the HTTP response includes the status code 404, the server returns the default 404 Not Found page.
-   Custom page: When the HTTP response includes the status code 404, the server returns the custom page. You must specify a full URL for the custom page.

**Note:**

-   Default pages for the status code 404 are classified as Alibaba Cloud public resources. No fees are charged for the default pages.
-   Custom pages are classified as personal resources. Fees are charged for the custom pages based on the specified billing rules.
-   For more information about 404 Not Found pages, see [Why does the 404 Not Found page appear?]().

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the management pane of the domain name, click **Cache**.

5.  Click the **Custom Pages** tab.

6.  On the **Custom Pages** tab, click **Customize**.

    ![Customize Page dialog box](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3826297061/p7276.png)

7.  In the Customize Page dialog box, set the required parameters.

    For example, you can store the `error404.html` page for the status code 404 in the same directory as the other static files on the origin server. This error page can be returned for requests that are addressed to the accelerated domain name `exp.aliyun.com`. In the Customize Page dialog box, select **404** from the Error Code drop-down list and enter the full URL `http://exp.aliyun.com/error404.html` in the Link field.

8.  Click **OK**.

    The newly configured error page appears on the **Custom Pages** tab. To modify or delete the error page, click **Modify** or **Delete** in the Actions column of the error page.


