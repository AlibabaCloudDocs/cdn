# Configure the refresh and prefetch features

Alibaba Cloud Content Delivery Network \(CDN\) allows you to refresh and prefetch resources. You can use the refresh feature to force the CDN nodes to retrieve the latest resources from the origin servers. You can use the prefetch feature to fetch frequently requested resources during off-peak hours. This accelerates content delivery. This topic describes how to configure the refresh and prefetch features and how to query the refresh and prefetch records.

The refresh and prefetch features can refresh resources from specific URLs and directories and prefetch resources from specific URLs.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Refresh & Prefetch**.

3.  On the Refresh and Prefetch page, click the **Refresh Cache** tab and set the following parameters to refresh or prefetch resources based on your business requirements.

    ![Refresh and prefetch resources](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9953470061/p88300.png)

    |Parameter|Description|
    |---------|-----------|
    |**Operation**|The operation that you want to perform. Supported options:     -   **Refresh**

After resources are updated on the origin server, you can refresh the URLs of the resources. The system then automatically clears the data of the resources that are cached on the CDN nodes. When clients visit the refreshed URLs, the corresponding CDN nodes redirect the requests to the origin server. Alibaba Cloud CDN then retrieves the latest resources from the origin server and returns them to the clients. The retrieved resources are also cached on the CDN nodes.

    -   **Prefetch**

You can prefetch frequently requested resources or less frequently visited accelerated domain names during off-peak hours to increase the cache hit ratio. |
    |**Object**|The type of the object that you want to refresh or prefetch. Supported options:     -   **Directory**

This option is available only when you set **Operation Type** to **Refresh**.

    -   **URL**

This option is available when you set **Operation Type** to **Refresh** or **Prefetch**. |
    |**URL**|When you enter URLs, take note of the following rules:**Note:** If you need to refresh or prefetch multiple URLs, enter one URL on each line.

    -   Refresh resources based on directories

Each URL must start with the string `http://` or `https://` and end with a forward slash \(/\).

You can refresh up to 100 directories with each Alibaba Cloud account per day. A maximum of 100 directories can be submitted at a time.

    -   Refresh resources based on URLs

Each URL must start with the string `http://` or `https://`.

You can refresh up to 2,000 URLs with each Alibaba Cloud account per day. A maximum of 1,000 URLs can be submitted at a time.

    -   Prefetch resources based on URLs

Each URL must start with the string `http://` or `https://`.

You can prefetch up to 500 URLs with each Alibaba Cloud account per day. A maximum of 100 URLs can be submitted at a time. |

4.  Click **Submit**.

5.  Click the **Records** tab.

6.  On the **Records** tab, specify a time range and an operation type, enter a domain name or a URL, and then click **Search**.

    You can check the refresh and prefetch records, including the refreshed or prefetched object, type, time, status, and progress of each operation.


## API operations

You can call API operations listed in the following table to refresh and prefetch resources.

|API|Description|
|---|-----------|
|[PushObjectCache](/intl.en-US/New API Reference/Refresh and preload operations/PushObjectCache.md)|Prefetches resources from origin servers to L2 CDN nodes. This reduces workloads on origin servers because users can hit cache upon their first visits.|
|[DescribeRefreshQuota](/intl.en-US/New API Reference/Refresh and preload operations/DescribeRefreshQuota.md)|Queries the maximum and remaining numbers of URLs and directories that can be refreshed, the maximum and remaining numbers of URLs that can be prefetched, and the maximum and remaining numbers of URLs and directories that can be blocked.|
|[DescribeRefreshTasks](/intl.en-US/New API Reference/Refresh and preload operations/DescribeRefreshTasks.md)|Queries the status of refresh or prefetch tasks under an accelerated domain name.|
|[RefreshObjectCaches](/intl.en-US/New API Reference/Refresh and preload operations/RefreshObjectCaches.md)|Refreshes files on CDN nodes. After a file is refreshed, it immediately becomes invalid. If a client requests the file, the CDN node redirects the request to the origin server to retrieve the latest version of the file. You can refresh resources based on multiple URLs in each call.|

