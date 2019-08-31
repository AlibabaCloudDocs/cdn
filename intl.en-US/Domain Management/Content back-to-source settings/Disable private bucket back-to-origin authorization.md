# Disable private bucket back-to-origin authorization {#task_187634 .task}

This topic describes how to revoke access permissions on your private bucket from an origin domain. You can revoke permissions for the corresponding roles to disable private bucket back-to-origin authorization in the Resource Access Management \(RAM\) console.

**Note:** If your CDN domain uses your private bucket as its origin, do not disable or delete this authorization method.

1.  Log on to the [RAM console](https://ram.console.aliyun.com/overview).
2.  In the left-side navigation pane, click **RAM Roles**.
3.  On the RAM Roles page, click RAM role name **AliyunCDNAccessingPrivateOSSRole**. 

    ![RAM roles](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5143/156726420345856_en-US.png)

4.  Click **Remove Permission** in the Actions column corresponding to the RAM role to be deleted. In the Remove Permission dialog box, click **OK**.
5.  Return to the RAM Roles page, click **Delete** in the Actions column corresponding to the RAM role to be deleted. 

    In the Delete RAM Role dialog box, click **OK**.


