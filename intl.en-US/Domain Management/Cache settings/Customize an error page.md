---
keyword: [custom page, customize an error page, CDN]
---

# Customize an error page

If a client requests a web service by using a browser and the requested URL does not exist, the website hosting server returns the default 404 Not Found page. To improve the default error page of a web server and overall user experience, you can associate complete URLs with error codes that are included in HTTP or HTTPS responses. When an error occurs, the server returns the specified custom page. This topic describes how to customize an error page.

Alibaba Cloud provides a default error page and supports custom error pages. In the following example, the 404 Not Found page is used to demonstrate the differences between a default error page and a custom error page.

-   Default page: When the HTTP response includes the 404 status code, the server returns the default 404 Not Found page.
-   Custom page: When the HTTP response includes the 404 status code, the server returns the custom page. You must specify the complete URL of the custom page.

**Note:**

-   Custom pages are classified as user resources. You are charged for the custom pages based on the specified billing rules.
-   For more information about 404 Not Found pages, see [Why does the 404 Not Found page appear?]()

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the management pane of the domain name, click **Cache**.

5.  Click the **Custom Pages** tab.

6.  On the **Custom Pages** tab, click **Customize**.

7.  In the **Customize Page** dialog box, select an HTTP status code and enter the URL of the custom page.

    The 404 status code is used in this example. For example, the 404 Not Found page `error404.html` and other static files are stored under the domain name of the origin server and requests are sent to the accelerated domain name `exp.aliyun.com`. In this case, you can select **404** and enter the complete URL of the custom page. The complete URL is `http://exp.aliyun.com/error404.html`.

    ![Customize an error page](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3826297061/p7276.png)

8.  Click **OK**.

    On the **Custom Pages** tab, you can click **Modify** or **Delete** in the Actions column to modify or delete a custom error page.


