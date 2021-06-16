# Manage the SLR for log storage

When you enable the log storage feature of Alibaba Cloud Content Delivery Network \(CDN\), the system automatically creates the service-linked role \(SLR\) AliyunServiceRoleForCDNLogDelivery. Alibaba Cloud CDN can assume this SLR to access resources in Object Storage Service \(OSS\) and Data Lake Analytics \(DLA\).

## Background information

AliyunServiceRoleForCDNLogDelivery is an SLR. After you enable the log storage feature of Alibaba Cloud CDN, Alibaba Cloud CDN must assume this SLR before Alibaba Cloud CDN can access resources in OSS and DLA. Alibaba Cloud CDN can assume the SLR to store log data in other services. Make sure that the geographic location where the log data is stored complies with the regulations. For more information about the SLR, see [Service-linked roles](/intl.en-US/RAM Role Management/Service-linked roles.md).

## Create AliyunServiceRoleForCDNLogDelivery

If this is the first time you enable the log storage feature of Alibaba Cloud CDN, the system automatically creates the SLR AliyunServiceRoleForCDNLogDelivery and attaches the permission policy AliyunServiceRolePolicyForCDNLogDelivery to the SLR. Alibaba Cloud CDN can assume the SLR to access OSS and DLA after the log storage feature is enabled. The SLR allows you to perform the following operations on OSS and DLA:

-   OSS: Create and query OSS buckets, write data to OSS buckets, query data in OSS buckets, and delete data from OSS buckets.
-   DLA: Enable, query, and disable DLA tasks.

**Note:** If the SLR AliyunServiceRoleForCDNLogDelivery is already created for Alibaba Cloud CDN, the system does not create the SLR again.

The following code block shows the content of the permission policy:

```
{

  "Version": "1",
  "Statement": [
    {
      "Action": [
        "openanalytics:CreateInstance",
        "openanalytics:UpgradeInstance",
        "openanalytics:ReleaseInstance",
        "openanalytics:ExecuteSQL",
        "openanalytics:QueryExecute",
        "openanalytics:DescribeVirtualCluster",
        "openanalytics:ListSparkJob",
        "openanalytics:GetJobStatus",
        "openanalytics:GetJobDetail",
        "openanalytics:GetJobLog",
        "openanalytics:KillSparkJob",
        "openanalytics:SubmitSparkJob"
      ],
      "Resource": "*",
      "Effect": "Allow"
    },
    {
      "Action": [
        "oss:PutBucket",
        "oss:GetBucketInfo"
      ],
      "Effect": "Allow",
      "Resource": "acs:oss:*:*:alicdn-log-delivery-*"
    },
    {
      "Action": [
        "oss:GetObject",
        "oss:PutObject"
      ],
      "Effect": "Allow",
      "Resource": "acs:oss:*:*:alicdn-log-delivery-*/alicdn-offline-log/*"
    },
    {
      "Action": "ram:CreateServiceLinkedRole",
      "Resource": "*",
      "Effect": "Allow",
      "Condition": {
        "StringEquals": {
          "ram:ServiceName": "openanalytics.aliyuncs.com"
        }
      }
    },
    {
      "Action": "ram:DeleteServiceLinkedRole",
      "Resource": "*",
      "Effect": "Allow",
      "Condition": {
        "StringEquals": {
          "ram:ServiceName": "logdelivery.cdn.aliyuncs.com"
        }
      }
    }
  ]
}
```

## Delete AliyunServiceRoleForCDNLogDelivery

If you no longer use the log storage feature and want to delete the SLR AliyunServiceRoleForCDNLogDelivery, perform the following steps:

1.  Disable log storage tasks

    1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

    2.  In the left-side navigation pane, choose **Logs** \> **Offline Logs**.

    3.  On the **Offline Logs** page, click the **Log Storage** tab.

    4.  Find the storage task that you want to disable and click **Disable Storage Task** in the Actions column.

    5.  In the dialog box that appears, click **OK**.

2.  Delete AliyunServiceRoleForCDNLogDelivery

    1.  Log on to the [RAM console](https://ram.console.aliyun.com/).

    2.  In the left-side navigation pane, click **RAM Roles**.

    3.  In the **RAM Role Name** column, find the SLR AliyunServiceRoleForCDNLogDelivery and click **Delete** in the Actions column.

        **Note:** If the SLR fails to be deleted, check whether log storage has been disabled.


