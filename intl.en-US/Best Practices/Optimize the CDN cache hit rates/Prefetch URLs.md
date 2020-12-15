---
keyword: cache hit ratio of Alibaba Cloud CDN
---

# Prefetch URLs

You can prefetch popular resources during off-peak hours, or prefetch resources for accelerated domain names that are not frequently visited. When clients request these resources again, CDN nodes return these resources to the clients. This way, the cache hit ratio of Alibaba Cloud Content Delivery Network \(CDN\) is increased.

[Alibaba Cloud account registration](https://account.alibabacloud.com/register/intl_register.htm) and [real-name verification](https://account-intl.console.aliyun.com/#/intlAuth) are completed.

CDN nodes serve as node resources shared by all Alibaba Cloud CDN users. You can set a time-to-live \(TTL\) value for each resource that is cached on a CDN node. This allows you to specify the validity period of resources that are cached on the CDN node. If your accelerated domain name is not frequently visited, the resources of the accelerated domain name may be removed from the CDN node before they expire. The least popular cached resources are the first to be stale in the cache. Popularity is indicated by how frequently a file is accessed on the node. If the file has low popularity, it may be removed before it expires.

-   The prefetch feature can be used to upload the specified URLs to L2 nodes in advance. When clients access an associated website again, the L2 nodes return the requested content to the clients without the need to retrieve the content from origin server. The prefetch feature does not increase the L1 hit ratio, but improves the overall hit ratio of Alibaba Cloud CDN.
-   The refresh feature can be used to clear the cache history of specific URLs or directories. This operation is often performed when the cached content on CDN nodes is stale after origin servers update the content with the same name. If a URL is refreshed, a request to the URL is redirected to the origin server during the visit that follows the refresh operation. Use the refresh feature with caution because this feature reduces the cache hit ratio.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Refresh & Prefetch**.

3.  Set **Operation** to **Prefetch** and enter **URL**.

4.  Click **Submit**.

5.  To check whether the cached resource can be hit, perform the following steps:

    1.  Open the browser Google Chrome and press F12.
    2.  In the panel that appears, click the **Network** tab.
    3.  Check the value of the `X-Cache` field in the response header of the specified URL.
        -   A value of `HIT` indicates that the resource that is cached on the CDN node is hit.
        -   A value of `MISS` indicates that the requested resource has not been cached on the CDN node and is retrieved from the origin server.

