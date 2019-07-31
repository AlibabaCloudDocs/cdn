# Customize an error page {#task_261642 .task}

This topic describes how to customize an error page. When a client requests a web service through a browser, the website hosting server generates a 404 Not Found page by default if the requested URL does not exist. However, you may not like the way the 404 Not Found page looks. To improve user experience, you can associate URLs with errors that are carried in HTTP or HTTPS responses, then the website hosting server generates the corresponding web pages when these errors are returned.

Alibaba Cloud CDN provides two types of error pages: default pages and custom pages. The differences between the default page and custom page are as follows:

-   Default page: When the HTTP response carries the 404 error, the server generates the 404 Not Found
-   Custom page: When the HTTP response carries the 404 error, the server generates the custom page.

**Note:** 

-   Default pages are considered Alibaba Cloud public resources and therefore are free of charge.
-   Custom pages are considered personal resources and therefore are charged.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com/overview).
2.  In the left-side navigation pane, click **Domain Names**.
3.  On the Domain Names page, find the domain name you want to set, and in the **Actions** column click **Manage**.
4.  In the left-side navigation pane, click **Cache**.
5.  On the Custom Pages tab page, click **Customize** and in the displayed dialog box set the parameters as prompted. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5148/15645669137276_en-US.png)

    Assume that you want to store the `error404.html` page for the 404 error together with other static files to the origin domain and access this web page through the accelerating domain `exp.aliyun.com`. Then you only need to select **404** from the **Error Code** drop-down list and enter the URL \(`http://exp.aliyun.com/error404.html`\) of the accelerating domain in the **Link** field.

6.  Click **OK**. 

    After the custom page is created, you can click **Modify** or **Delete** in the **Actions** column to modify or delete the custom page.


