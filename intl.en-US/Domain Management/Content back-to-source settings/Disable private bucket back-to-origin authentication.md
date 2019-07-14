# Disable private bucket back-to-origin authentication {#task_187634 .task}

This topic describes how to disable private bucket back-to-origin authentication on the Resource Access Management \(RAM\) console. This authentication method enables your domain to access the resources in your private bucket.

**Note:** If your domain uses your private bucket as its origin, do not disable or remove this authentication method.

1.  Log on to the [RAM console](https://ram.console.aliyun.com/overview).
2.  In the left-side navigation pane, click **RAM Roles**.
3.  On the RAM Roles page, click the name of your RAM role and in the **Actions** column click **Remove Permission**. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5143/156310352345856_en-US.png)

4.  In the Remove Permission dialog box, click **OK**.
5.  Return to the RAM Roles page, find your RAM role, and in the **Actions** column click **Delete**.
6.  In the Delete RAM Role dialog box, click **OK**. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5143/156310352345859_en-US.png)

    For information about how to enable private bucket back-to-origin authentication, see [Enable private bucket back-to-origin authentication](reseller.en-US/Domain Management/Content back-to-source settings/Enable private bucket back-to-origin authentication.md#).


