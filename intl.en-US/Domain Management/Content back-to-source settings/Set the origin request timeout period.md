# Set the origin request timeout period {#task_1130280 .task}

This topic describes how to set the origin request timeout period. Specifically, the period of time in which CDN nodes wait for back-to-origin requests. The default timeout period is 30 seconds. Note that if a CDN node does not receive any requests from an origin within the specified timeout period, the CDN node disconnects itself from the origin.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com/overview).
2.  In the left-side navigation pane, click **Domain Names**.
3.  On the Domain Names page, find the domain name you want to set, and click **Manage** in the **Actions** column.
4.  In the left-side navigation pane, click **Back-to-origin**.
5.  In the Origin Request Timeout section, click **Modify**.
6.  In the Origin Request Timeout dialog box, set Timeout Value. 

    **Note:** 

    -   The timeout period of back-to-origin requests directed to CDN nodes does not exceed 100 seconds.
    -   You must set the timeout period to a value less than or equal to 900 seconds.
    ![回源请求超时时间](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/908787/156463863151614_en-US.png)

7.  Click **OK**.

