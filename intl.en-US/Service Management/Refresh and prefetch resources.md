# Refresh and prefetch resources

Alibaba Cloud CDN allows you to prefetch and refresh resources. You can refresh resources to delete expired resources on CDN nodes. After expired resources are deleted from CDN nodes, requests are redirected to the origin servers to retrieve the latest version of the resources. You can also prefetch frequently requested resources during off-peak hours from the origin servers to CDN nodes. This accelerates the delivery of these resources.

## Overview

Alibaba Cloud CDN supports the refresh and prefetch features. The following section describes how these features work:

-   Refresh

    A refresh task deletes all resources that are cached on CDN nodes. After cached resources are deleted, when a CDN node receives a request, the CDN node redirects the request to the origin server to retrieve the requested resources. The retrieved resources are returned to the client and cached on the CDN node. The refresh feature reduces the cache hit ratio.

-   Prefetch

    A prefetch task prefetches resources from origin servers and caches the resources on CDN nodes. When a CDN node receives a request, the CDN node directly returns the requested resources to the client because the resources are already cached on CDN nodes. The prefetch feature increases the cache hit ratio.


## Scenarios

The following table describes the scenarios where the refresh or prefetch feature is commonly used.

|Feature|Scenario|
|-------|--------|
|Refresh|-   **Update and release resources**

After resources on your origin server are updated, you can submit the URLs or directories of the updated resources to Alibaba Cloud CDN. Then, Alibaba Cloud CDN refreshes the resources that are cached on CDN nodes. This ensures that users can retrieve up-to-date resources from CDN nodes.

-   **Delete resources that violate the limits of Alibaba Cloud CDN**

After you delete resources that violate the limits described in [Content moderation](/intl.en-US/Product Introduction/Limits.md) from your origin server, users can still access the resources because they are cached on CDN nodes. In this case, you must submit the URLs of the resources to Alibaba Cloud CDN to update the CDN cache. |
|Prefetch|-   **Promote events**

Before you hold a major event, you can push the static resources of the event page to CDN nodes. After the event starts, users can access the static resources, which are already cached on CDN nodes. This accelerates content delivery.

-   **Release installation packages**

Before you release an installation or an upgrade package of a product, you can push the resources of the package to CDN nodes. After the product is launched, users can download the package from CDN nodes. This accelerates content delivery and reduces loads on the origin server when a large number of users want to access your resources. |

## Usage notes

-   After a refresh task is submitted and completed, some resources are deleted from CDN nodes. When a CDN node receives a request for the deleted resources, the CDN node redirects the request to the origin server to retrieve the resources. Then, the retrieved resources are returned to the client and cached on the CDN node again. After multiple refresh tasks, a large amount of resources are deleted from CDN nodes. This increases the number of requests that are redirected to the origin server, the amount of bandwidth resources consumed by the back-to-origin process, and loads on the origin server.
-   After a refresh task is submitted and completed, L2 CDN nodes immediately start retrieving resources from the origin server. Therefore, a large number of refresh tasks cause a large number of concurrent download tasks. This increases the number of requests that are redirected to the origin server, the amount of bandwidth resources consumed by the back-to-origin process, and loads on the origin server.

## Refresh resources

For more information about how to automate refresh and prefetch tasks, see [Run a script to prefetch content](/intl.en-US/New API Reference/Refresh and preload operations/Run a script to prefetch content.md).

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Refresh & Prefetch**.

3.  On the **Refresh Cache** tab, create a refresh task.

    ![Refresh and prefetch resources](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/0863759161/p88300.png)

    |Parameter|Description|
    |---------|-----------|
    |**Operation**|Select **Refresh**.|
    |**Object**|You can select **URL** or **Directory**.|
    |**URL**|    -   Refresh resources based on URLs
        -   Each URL must start with the string `http://` or `https://`.
        -   Enter only one URL on each line.
        -   Each Alibaba Cloud account can submit at most 2,000 URLs per day, and at most 1,000 URLs at a time. You can submit at most 1,000 URLs for each domain name per minute.

If your daily peak bandwidth exceeds 200 Mbit/s, you can [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex) to request a quota increase. Alibaba Cloud determines whether to approve your application based on your business requirements.

    -   Refresh resources based on directories
        -   Each URL must start with the string `http://` or `https://` and end with a forward slash \(/\).
        -   Enter only one URL on each line.
        -   Each Alibaba Cloud account can submit at most 100 directories per day, and at most 100 directories at a time. Subdirectories are supported. You can apply for a quota increase. After your application is approved, you can submit at most 1,000 directories at a time.

If your daily peak bandwidth exceeds 200 Mbit/s, you can [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex) to request a quota increase. Alibaba Cloud determines whether to approve your application based on your business requirements. |

4.  Click **Submit**.

5.  Check the refresh progress.

    After you submit a refresh task, you can check the progress and details on the **Records** tab. The progress is affected by the number of subjects to be refreshed. It may take some time to complete the task.

    **Note:** If **Auto CDN Cache Update** is enabled in the Object Storage Service \(OSS\), you cannot check the automatic refresh tasks in the Alibaba Cloud CDN console.


## Prefetch resources

For more information about how to automate refresh and prefetch tasks, see [Run a script to prefetch content](/intl.en-US/New API Reference/Refresh and preload operations/Run a script to prefetch content.md).

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Refresh & Prefetch**.

3.  On the **Refresh Cache** tab, create a prefetch task.

    ![Prefetch resources](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9585051261/p267536.png)

    |Parameter|Description|
    |---------|-----------|
    |**Operation**|Select **Prefetch**.|
    |**Object**|Only **URL** is supported.|
    |**URL**|    -   Each URL must start with the string `http://` or `https://`.
    -   Enter only one URL on each line.
    -   Each Alibaba Cloud account can submit at most 500 URLs per day, and at most 100 URLs at a time.

If your daily peak bandwidth exceeds 500 Mbit/s, you can [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex) to request a quota increase. Alibaba Cloud determines whether to approve your application based on your business requirements.

    -   The prefetch queue of each Alibaba Cloud account can contain at most 100 URLs. Alibaba Cloud CDN performs prefetch tasks in order of submittal time of the URLs. |

4.  Click **Submit**.

5.  Check the prefetch progress

    After you submit a prefetch task, you can view the progress and details on the **Records** tab. The progress is affected by the number of subjects to be prefetched. It may take some time to complete the task.


## Related API operations

You can call API operations listed in the following table to refresh and prefetch resources.

|API|Description|
|---|-----------|
|[PushObjectCache](/intl.en-US/New API Reference/Refresh and preload operations/PushObjectCache.md)|Prefetches resources from origin servers to L2 CDN nodes. This reduces loads on origin servers because users can hit cache upon their first visits.|
|[RefreshObjectCaches](/intl.en-US/New API Reference/Refresh and preload operations/RefreshObjectCaches.md)|Refreshes files on CDN nodes. After a file is refreshed, the version cached on CDN nodes immediately expires. When a client requests the file, the CDN node redirects the request to the origin server to retrieve the latest version of the file. Alibaba Cloud CDN allows you to refresh content of multiple URLs at a time.|
|[DescribeRefreshTasks](/intl.en-US/New API Reference/Refresh and preload operations/DescribeRefreshTasks.md)|Queries the status of refresh or prefetch tasks that belong to an accelerated domain name.|
|[DescribeRefreshTaskById](/intl.en-US/New API Reference/Refresh and preload operations/DescribeRefreshTaskById.md)|Queries the status of refresh or prefetch tasks by ID for an accelerated domain name.|
|[DescribeRefreshQuota](/intl.en-US/New API Reference/Refresh and preload operations/DescribeRefreshQuota.md)|Queries the maximum and remaining numbers of URLs and directories that can be refreshed, the maximum and remaining numbers of times that you can prefetch content, and the maximum and remaining numbers of URLs and directories that can be blocked on the current day.|

