# Preload URLs {#task_878830 .task}

You can preload popular resources before the business peak, or preload resources for CDN domains that are not frequently visited. When you access these resources again, you can directly retrieve them from the CDN node. In this way, the CDN cache hit rate is increased.

CDN nodes serve as node resources shared by all CDN users. A cache rule configured on CDN indicates the maximum cache duration for the corresponding resources on CDN. If your CDN domain is not frequently visited, the resources of the CDN domain may be removed from the cache of the CDN node before they expire. The least popular cached resources are the first to be stale in the cache. Popularity refers to how frequently a file is accessed on the node. If the file is not popular enough, it may be removed before it expires.

-   The preload feature uploads the specified URLs to the CDN L2 nodes in advance. When you access an associated website again, you do not need to retrieve the requested resources from the origin server. Although the preload feature does not directly increase the L1 hit rate, it improves the real hit rate of CDN.
-   The refresh feature clears the cache history of specific URLs or directories. This operation is often performed when the cached content on CDN is stale after the origin server updates the content with the same name. After the refresh operation, the request to the URL will be directly rerouted to the origin server at the next visit. Use the CDN refresh feature with caution because this feature reduces the cache hit rate.

1.  Log on to the [Alibaba Cloud CDN console](https://partners-intl.aliyun.com/login-required#cdn).
2.  In the left-side navigation pane, click **Refresh**. 

    ![](images/56840_en-US_source.png)

3.  Set the **Operation** parameter to **Preload**, and enter **URLs**.
4.  Click **Submit**.

