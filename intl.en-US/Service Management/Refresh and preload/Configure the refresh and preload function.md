# Configure the refresh and preload function {#task_187634 .task}

Alibaba Cloud CDN supports resource refresh and preload. You can use the refresh function to force the CDN nodes to obtain the latest files from the origin. You can use the preload function to preload popular resources during business peak hours, improving resource access efficiency. This topic describes how to enable the refresh and preload function, and how to query the operation records.

The refresh and preload function supports URL refresh, directory refresh, and URL preload. For more information, see [Overview](reseller.en-US/Service Management/Refresh and preload/Overview.md#).

1.  Log on to the [Alibaba Cloud CDN console](https://partners-intl.aliyun.com/login-required#cdn).
2.  In the left-side navigation pane, click **Refresh**.
3.  On the Refresh Cache tab, configure the refresh or preload function as needed. 

    |Parameter|Description|
    |---------|-----------|
    |Operation|Operation types:     -   Refresh

When you refresh the URLs for resources updated in the origin, the system automatically clears junk data on the CDN nodes. When the URLs are accessed again, the latest resources are obtained directly from the origin and cached to the CDN nodes.

    -   Preload

You can preload popular resources or CDN domains with low traffic during off-peak hours to increase the cache hit ratio.

 |
    |Object|Object types:     -   Directory

When Operation is set to Refresh, you must set this parameter.

    -   URL

When Operation is set to Refresh or Preload, you must set this parameter.

 |
    |URL|When you need to refresh or preload multiple URLs, enter one URL per line. When you enter the URLs, note the limits for the following operations:     -   Directory refresh

Each URL must start with `http://` or `https://`, and end with `/`.

A single Alibaba Cloud account can refresh up to 100 directories per day. This can be done at one time.

    -   URL refresh

Each URL must start with `http://` or `https://`.

A single Alibaba Cloud account can refresh up to 2,000 URLs per day. Each refresh operation can refresh up to 1,000 URLs each time.

    -   URL preload

Each URL must start with `http://` or `https://`.

A single Alibaba Cloud account can preload up to 500 URLs per day. Each preload operation can preload up to 100 URLs each time.

 |

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5168/15672610623428_en-US.png)

4.  Click **Submit**.
5.  Click the **Records** tab.
6.  On the Records tab, set the time range and operation type, enter a domain name or URL, and then click **Search**. 

    You can check the resource refresh and preload records, including target, operation type, operation time, status, and progress.


