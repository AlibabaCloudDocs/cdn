# Set the back-to-origin request timeout

If a client requests content that is not cached on the Alibaba Cloud Content Delivery Network \(CDN\) node, the node retrieves the content from the origin server that serves the content. This topic describes how to set the back-to-origin request timeout. The back-to-origin request timeout value specifies the amount of time that the CDN node waits for a response after a request is redirected to the origin server. The default back-to-origin request timeout value is 30 seconds. If the CDN node does not receive a response within the specified timeout period, the CDN node disconnects from the origin server.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the management pane of the domain name, click **Back-to-origin**.

5.  In the **Back-to-origin Request Timeout** section, click **Modify**.

6.  In the **Back-to-origin Request Timeout** dialog box, set Timeout Value.

    ![Back-to-origin request timeout value](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6846219951/p51614.png)

    The maximum timeout value is set to 900 seconds. When Alibaba Cloud CDN communicates with origin servers as expected, the back-to-origin request timeout period is no more than 100 seconds.

7.  Click **OK**.


