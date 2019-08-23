# Customize an error page {#task_261642 .task}

When a client requests a Web service through a browser, the website hosting server generates a 404 Not Found page if the requested URL does not exist. However, you may not like the way the 404 Not Found page looks. To improve user experience, you can associate URLs with errors that are carried in HTTP or HTTPS responses, then the server returns the corresponding web pages when these errors are returned. This topic describes how to customize an error page.

Alibaba Cloud CDN provides two types of error pages: default page and custom page. The differences between the default page and custom page are as follows:

-   Default page: When the HTTP response carries the 404 error, the server generates the default 404 Not Found page.
-   Custom page: When the HTTP response carries the 404 error, the server generates the custom page. You must specify a full URL for the custom page.

**Note:** 

-   Default pages are considered Alibaba Cloud public resources and are free of charge.
-   Custom pages are considered personal resources and are charged.

1.  Log on to the [Alibaba Cloud CDN console](https://partners-intl.aliyun.com/login-required#cdn).
2.  In the left-side navigation pane, click **Domain Names**.
3.  On the Domain Names page, find the target domain name and click **Manage**.
4.  In the left-side navigation pane of the specified domain, click **Cache**.
5.  Click **Custom Pages**.
6.  On the Custom Pages tab, click **Customize**. 

    ![Custom Pages](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5148/15665311367276_en-US.png)

7.  In the Customize Page dialog box that appears, set the parameters. Assume that you want to store the `error404.html` page for the 404 error together with other static files to the origin domain and access this web page through the accelerating domain `exp.aliyun.com`. Then, you only need to select **404** from the Error Code drop-down list and enter the URL \(`http://exp.aliyun.com/error404.html`\) of the accelerating domain in the Link field.
8.  Click **OK**. 

    After the custom page is created, you can click **Modify** or **Delete** in the Actions column to modify or delete the custom page.


