# Authorize a RAM user to prefetch and refresh resources

By default, Resource Access Management \(RAM\) users do not have permissions to prefetch or refresh resources. You can attach system or custom permission policies to a RAM user to allow the RAM user to prefetch and refresh resources.

A RAM user is created. If no RAM user is created, create one. For more information, see [Create a RAM user](/intl.en-US/RAM User Management/Basic operations/Create a RAM user.md).

By default, RAM users do not have permissions to prefetch or refresh resources. If you log on to the Alibaba Cloud Content Delivery Network \(CDN\) console and attempt to prefetch or refresh resources as a RAM user, the following error message appears: **The account does not have access to the page interface, or the interface does not support RAM access control**. In this case, you must grant the required prefetch and refresh permissions to the RAM user.

![Error message](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4174064261/p285875.png)

RAM supports two types of permission policy: system permission policy and custom permission policy. You can attach a system or custom permission policy to the RAM to allow the RAM user to prefetch and refresh resources.

-   System permission policy

    System permission policies are automatically created by Alibaba Cloud and cannot be modified. A system permission policy grants RAM users full permissions on Alibaba Cloud CDN. System permission policies simplify the authorization process. For more information about how to attach a system permission policy to a RAM user, see [Method 1: Attach a system permission policy to a RAM user](#section_7l8_9g8_u83).

-   Custom permission policy

    You can create, update, and manage custom permission policies based on business requirements. Custom permission policies grant RAM users only specified permissions. For example, you can use a custom permission policy to allow a RAM user only to prefetch and refresh resources, or manage the log storage feature. In this case, the RAM user does not have permissions to perform operations other than the authorized ones. For more information about how to attach a custom permission policy to a RAM user, see [Method 2: Attach a custom permission policy to a RAM user](#section_sx6_c72_162).


## Method 1: Attach a system permission policy to a RAM user

1.  Log on to the [RAM console](https://ram.console.aliyun.com).

2.  In the left-side navigation pane, choose **Identities** \> **Users**.

3.  On the Users page, find the RAM user to which you want to grant permissions and click **Add Permissions** in the **Actions** column.

    ![Add permissions](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/0015164261/p283901.png)

4.  In the **Add Permissions** penal, set the following parameters.

    ![Add a system permission policy](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/0015164261/p283951.png)

    1.  Set Authorized Scope to **Alibaba Cloud Account**.

    2.  Click the **System Policy** tab.

    3.  Enter AliyunCDN in the search box. The system automatically displays all permission policies that are related to Alibaba Cloud CDN.

    4.  Click **AliyunCDNFullAccess** to add the policy to the **Selected** list.

        **Note:** The **AliyunCDNFullAcces** permission policy grants the RAM user full permissions on Alibaba Cloud CDN. The RAM user has permissions to call CDN API operations and manage all accelerated domain names.

5.  Click **OK**.

6.  Click **Complete**.


## Method 2: Attach a custom permission policy to a RAM user

1.  Create a custom permission policy.

    1.  Log on to the [RAM console](https://ram.console.aliyun.com).

    2.  In the left-side navigation pane, choose **Permissions** \> **Policies**.

    3.  On the Policies page, click **Create Policy**.

    4.  Create a custom permission policy

        ![Create a custom permission policy](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/0015164261/p284018.png)

        |Parameter|Description|
        |---------|-----------|
        |**Policy Name**|Enter a name that is descriptive and easy to identify. AliyunCdnRefresh is used in this example.|
        |**Note**|Optional. Enter remarks for the permission policy.|
        |**Configuration Mode**|Select **Script**. This mode supports more flexible configurations.|
        |**Policy Document**|Enter the following content. This permission policy grants the RAM user permissions on the prefetch and refresh API operations. The RAM user can call API operations to prefetch or refresh resources.         ```
{
  "Version": "1",
  "Statement": [
    {
      "Action": [
        "cdn:PushObjectCache",
        "cdn:RefreshObjectCaches",
        "cdn:DescribeRefreshTasks",
        "cdn:DescribeRefreshQuota"
      ],
      "Resource": "acs:cdn:*:*:*",
      "Effect": "Allow"
    }
  ]
}
        ```

**Note:**

        -   All API operations of Alibaba Cloud CDN can be defined in custom permission policies. You can add other API operations to custom permission policies based on your business requirements. After you attach these policies to RAM users, the RAM users have permissions to call the specified API operations. For more information about the actions that you can authorize RAM users to perform, see [RAM authorization](/intl.en-US/New API Reference/RAM authorization.md).
        -   The policy content must be expressed in a specific syntax structure to describe the authorized resource sets, operation sets, and authorization conditions. For more information, see [Policy structure and syntax](/intl.en-US/Policy Management/Policy language/Policy structure and syntax.md) and [Policy elements](/intl.en-US/Policy Management/Policy language/Policy elements.md). |

    5.  Click **OK**.

2.  Grant permissions to the RAM user.

    1.  Log on to the [RAM console](https://ram.console.aliyun.com).

    2.  In the left-side navigation pane, choose **Identities** \> **Users**.

    3.  On the Users page, find the RAM user to which you want to grant permissions and click **Add Permissions** in the **Actions** column.

        ![Add permissions](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/0015164261/p283901.png)

    4.  In the **Add Permissions** penal, set the following parameters.

        ![Add permissions](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/0015164261/p284024.png)

        |Parameter|Description|
        |---------|-----------|
        |**Authorized Scope**|Select **Alibaba Cloud Account**, which specifies that the authorized scope is all resources that belong to the current Alibaba Cloud account. Do not select **Specific Resource Group**.|
        |**Principal**|The current RAM user is selected by default.|
        |**Select Policy**|Click the **Custom Policy** tab. Enter the name of the custom permission policy created in [Step 1](#step_dsb_1z0_5lx). The name of the custom permission policy in this example is AliyunCdnRefresh. After the system displays the policy, click its name to add it to the **Selected** list.|

    5.  Click **OK**.

    6.  Click **Complete**.


[Log on to the console as a RAM user](/intl.en-US/RAM User Management/Logon management/Log on to the console as a RAM user.md)

