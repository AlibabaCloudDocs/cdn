# Create RAM user accounts for CDN {#task_261642 .task}

You can use Resource Access Management \(RAM\) user accounts and resource groups to isolate and manage resources. This topic describes how to create RAM user accounts for CDN and grant these accounts access permissions to resource groups.

1.  Use your Alibaba Cloud account to log on to the [Enterprise console](https://enterprise.console.aliyun.com/). 

    For more information about how to use the Enterprise console, see [Enterprise console user guide](https://help.aliyun.com/document_detail/59910.html).

    **Note:** In the Enterprise console, create a RAM user account, create a resource group, and then authorize the RAM user account. Use the RAM user account to log on to the CDN console. The RAM user account can only view and manage resources that it is authorized to access. In this way, resources are isolated and resource access control is implemented.

    ![](images/3487_en-US.png)

2.  Create a RAM user account. 
    1.  Log on to the Enterprise console. In the left-side navigation pane, choose **Directory** \> **Identities**. 

        You can also create groups to manage multiple RAM user accounts.

        ![](images/3488_en-US.png)

        **Note:** If this is the first time that you have logged on to the Directory page, you must create a directory. Each account can have only one directory.

    2.  On the Identities page, click **Create Internal Account**. 

        ![](images/51346_en-US.png)

    3.  Enter the RAM user account information according to the instructions on the page.
    4.  Click **OK**.
3.  Create a resource group. 
    1.  Log on to the Enterprise console. In the left-side navigation pane, choose **Resource Management**. 

        ![](images/51347_en-US.png)

    2.  Select Resource Groups, and then click **Create Resource Group**. 

        ![](images/51349_en-US.png)

    3.  Enter the resource group information according to the instructions on the page.
    4.  Click **OK**.
4.  Add resources to the resource group. 
    1.  Click **Manage Resources** for the created resource group. 

        ![Manage resources](images/54431_en-US.png)

    2.  Click the Resources tab, and then set Service to CDN.
    3.  Select the CDN domain names that you want to add to the resource group, and then click **Transfer Resource In**.
    4.  Click **OK**.
5.  Authorize the RAM user account. 
    1.  Click **Manage Resources** for the created resource group.
    2.  Click the Permissions tab, and then click **Set Permissions**. 

        ![](images/51353_en-US.png)

    3.  Select the RAM user account that you want to authorize. 

        Use AliyunCDNFullAccess to grant a RAM user account CDN management permissions.

        The following authorization policies are provided:

        -   AliyunCDNFullAccess: CDN management permissions. This policy grants you the permissions to add, modify, delete, and view resources.

            ``` {#codeblock_9gg_mw3_rw7}
            {
              "Version": "1",
              "Statement": [
                {
                  "Action": "cdn:*",
                  "Resource": "*",
                  "Effect": "Allow"
                }
              ]
            }
            ```

        -   AliyunCDNReadOnlyAccess: CDN read-only permission.

            ``` {#codeblock_3n6_4xn_m6z}
            {
              "Version": "1",
              "Statement": [
                {
                  "Action": "cdn:Describe*",
                  "Resource": "*",
                  "Effect": "Allow"
                }
              ]
            }
            ```

    4.  Click **OK**.
6.  Use the RAM user account to log on to the CDN console. 

    Logon address: [http://signin.aliyun.com/Custom domain.onaliyun.com/login.htm](http://signin.aliyun.com/%3C%E8%87%AA%E5%AE%9A%E4%B9%89%E5%9F%9F%3E.onaliyun.com/login.htm).

    After you log on to the CDN console, all resource groups that the RAM user account can access are shown. CDN domain names are listed by resource group.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5176/15671569163493_en-US.png)

    RAM user accounts cannot use the illicit content moderation function of CDN. They can use other functions in the same way as Alibaba Cloud accounts. For more information, see [Domains](../DNCDN11828177/EN-US_TP_5118.dita#concept_tvm_vhx_wdb) and [Services](EN-US_TP_1162242.dita#concept_1461607).


