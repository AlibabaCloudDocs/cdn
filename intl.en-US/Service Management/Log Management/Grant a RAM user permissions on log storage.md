# Grant a RAM user permissions on log storage

By default, Resource Access Management \(RAM\) users do not have permissions to activate or manage the log storage feature of Dynamic Route for CDN \(DCDN\). If you want to allow a RAM user to activate or manage log storage, you must grant the RAM user the required permissions. You can use permission policies to regulate access control.

RAM is an identity management and access control service that is provided by Alibaba Cloud. RAM allows you to create and manage RAM users for employees, systems, applications, and other identities. You can manage the permissions of RAM users to control their access to Alibaba Cloud resources.

## Scenarios

In this topic, a permission policy is used to grant a RAM user full permissions on log storage. The permission policy allows the RAM user to enable, manage, query, modify, and disable log storage.

**Note:** The logic of the API operations that are related to log storage is complex and involves multiple services. Therefore, the API operations described in this topic are not available for use. We recommend that you perform operations in the DCDN console.

## Step 1: Create a custom permission policy

1.  Log on to the [RAM console](https://ram.console.aliyun.com/).

2.  In the left-side navigation pane, choose **Permissions** \> **Policies**.

3.  On the Policies page, click **Create Policy**.

4.  Define the permission policy.

    ![Create a custom permission policy](../images/p241583.png "Create a custom permission policy")

    |Parameter|Description|
    |---------|-----------|
    |**Policy Name**|Enter an informative name for easy identification.|
    |**Note**|Optional. Enter remarks for the permission policy.|
    |**Configuration Mode**|Select **Script**. This mode which supports more flexible configurations.|
    |**Policy Document**|Enter content for the permission policy. You do not need to import existing policies. The following table describes how to define the permission policy.|

    Grant the RAM user full permissions on the log storage feature. Allow the RAM user to enable, manage, query, modify, and disable log storage. The following code block shows the content of the permission policy:

    **Note:** If you want to grant specified permissions to a RAM user, specify only the permissions that you want to grant.

    ```
    {
        "Statement": [
            {
                "Action": "ram:CreateServiceLinkedRole",
                "Resource": "acs:ram:*:*:role/*",
                "Effect": "Allow",
                "Condition": {
                    "StringEquals": {
                        "ram:ServiceName": [
                            "logdelivery.cdn.aliyuncs.com"
                        ]
                    }
                }
            },
            {
                "Effect": "Allow",
                "Action": [
                    "cdn:DescribeUserDomains",
                    "cdn:CreateCdnDomainOfflineLogDelivery",
                    "cdn:DescribeCdnOfflineLogDeliveryStatus",
                    "cdn:DescribeCdnOfflineLogDelivery",
                    "cdn:DescribeCdnOfflineLogDeliveryField",
                    "cdn:DescribeCdnOfflineLogDeliveryRegions",
                    "cdn:DisableCdnDomainOfflineLogDelivery",
                    "cdn:DisableCdnOfflineLogDelivery",
                    "cdn:EnableCdnDomainOfflineLogDelivery"
                ],
                "Resource": "acs:cdn:*:*:*"
            }
        ],
        "Version": "1"
    }
    ```

    The following table describes the API operations that can be defined in a custom permission policy.

    |API|Required|Function|Description|
    |---|--------|--------|-----------|
    |DescribeUserDomains|Yes|Queries all domain names that are added to Alibaba Cloud CDN.|If you grant a RAM user permissions on this API operation, the RAM user can query all domain names that are added to Alibaba Cloud CDN, and configure log storage for these domain names.|
    |CreateCdnDomainOfflineLogDelivery|No|Enables log storage.|If you do not want a RAM user to enable log storage, do not grant the RAM user permissions on this API operation.|
    |DescribeCdnOfflineLogDeliveryStatus|Yes|Queries whether log storage is enabled.|RAM users require permissions on this API operation if they want to query whether log storage is enabled, or enable log storage.|
    |DescribeCdnOfflineLogDelivery|Yes|Queries domain names that have log storage enabled.|If you grant a RAM user permissions on this API operation, the RAM user can query domain names that have log storage enabled.|
    |DescribeCdnOfflineLogDeliveryField|Yes|Queries fields that are supported by log storage.|RAM users require permissions on this API operation if they want to query or enable log storage.|
    |DescribeCdnOfflineLogDeliveryRegions|Yes|Queries regions in which log storage is supported.|N/A|
    |DisableCdnDomainOfflineLogDelivery|No|Disables domain names that have log storage enabled.|If you grant a RAM user permissions on this API operation, the RAM user can disable domain names that have log storage enabled. Proceed with caution.|
    |EnableCdnDomainOfflineLogDelivery|No|Creates a log storage task for a domain name.|If you grant a RAM user permissions on this API operation, the RAM user can create a log storage task for a domain name. Proceed with caution.|
    |DisableCdnOfflineLogDelivery|No|Disables log storage.|If you grant a RAM user permissions on this API operation, the RAM user can disable log storage. If you want to use log storage again, you must enable and configure log storage. Proceed with caution.|

5.  Click **OK**.


## Step 2: Grant permissions to the RAM user

1.  Log on to the [RAM console](https://ram.console.aliyun.com/).

2.  [Create a RAM user](/intl.en-US/RAM User Management/Basic operations/Create a RAM user.md).

    **Note:** If you have already created a RAM user, skip this step.

3.  In the left-side navigation pane, choose **Identities** \> **Users**.

4.  On the Users page, find the RAM user to which you want to grant permissions and click **Add Permissions** in the **Actions** column.

5.  In the **Add Permissions** penal, set the following parameters.

    ![Add permissions](../images/p211004.png "Add permissions")

    |Parameter|Description|
    |---------|-----------|
    |**Authorized Scope**|Select **Alibaba Cloud Account**, which specifies that the authorized scope is all resources that belong to the current Alibaba Cloud account. Do not select **Specific Resource Group**.|
    |**Principal**|The current RAM user is selected by default.|
    |**Select Policy**|Select **Custom Policy**, and click the name of the custom policy created in [Step 1](#section_av0_prw_uz3). The custom policy is then added to the right-side **Selected** list.|

6.  Click **OK**.

7.  Click **Complete**.


[Log on to the console as a RAM user](/intl.en-US/RAM User Management/Logon management/Log on to the console as a RAM user.md)

