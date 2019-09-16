# Overview {#concept_845410 .concept}

A low CDN cache hit rate imposes heavy pressure on the origin server and causes low access efficiency of static resources. You can select an optimization policy to improve the CDN cache hit rate based on the specific cause of the low CDN cache hit rate.

CDN accelerates the delivery of static resources by caching the static resources to the nearest CDN node. When your client accesses a resource, the CDN node serves the requested resource directly from the cache without retrieving the resource from the origin server. Therefore, the CDN cache hit rate directly affects user experience, and ensuring a high cache hit rate has become the key topic of CDN.

CDN cache hit rates include the byte cache hit rate and request cache hit rate.

-   Byte cache hit rate = Number of bytes returned from the CDN cache/Number of bytes returned for all CDN requests

    **Note:** The lower the byte cache hit rate, the higher the back-to-origin traffic. The higher the outbound traffic of the origin server, the larger the bandwidth and other loads of the origin server. Therefore, back-to-origin traffic represents the load pressure on the origin server, and the byte cache hit rate is the main concern in actual business scenarios.

-   Request cache hit rate = Number of requests that hit the CDN cache/Number of all CDN requests

## View the CDN cache hit rates {#section_o96_ep0_dzz .section}

You can use either of the following methods to view the CDN cache hit rates.

-   By using the console

    The CDN console provides the resource monitoring feature to display the byte cache hit rate, as shown in the following figure.

    ![Console interface](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5281/156860477248984_en-US.png)

-   By checking logs

    In the CDN request logs, CDN records the cache hit status of all CDN requests. For more information about the log format, see [Download logs](../../../../reseller.en-US/Service Management/Log Management/Download logs.md#). The cache hit status field is displayed as either HIT or MISS. A sample log entry is as follows.

    ``` {#codeblock_xfv_445_fjx}
    26/Jun/2019:10:38:19 +0800] 192.168.53.146 - 1542 "-" "GET http://www.aliyun.com/index.html" 200 191 2830 MISS "Mozilla/5.0 (compatible; AhrefsBot/5.0; +http://ahrefs.com/robot/)" "text/html"
    ```

    **Note:** The hit status only indicates the hit status of the CDN L1 node. For example, if the requested resource is not found in the cache of the CDN L1 node but is found in the cache of the CDN L2 node, the hit status is still displayed as MISS.

-   By using the API

    To query the byte cache hit rate of CDN, call the [../../../../dita-oss-bucket/SP\_19/DNCDN18101146/EN-US\_TP\_65080.md\#](../../../../reseller.en-US/New API Reference/Data monitoring operations/DescribeDomainHitRateData.md#) operation. To query the request cache hit rate of CDN, call the [../../../../dita-oss-bucket/SP\_19/DNCDN18101146/EN-US\_TP\_65082.md\#](../../../../reseller.en-US/New API Reference/Data monitoring operations/DescribeDomainReqHitRateData.md#) operation.


## Optimize the CDN cache hit rates {#section_nc4_hok_6xt .section}

The following table describes the causes of a low cache hit rate and the corresponding optimization policies.

|Optimization policy|Causes of a low CDN cache hit rate|
|-------------------|----------------------------------|
|[Preload URLs](reseller.en-US/Best Practices/Optimize the CDN cache hit rates/Preload URLs.md#)| -   During peak business hours, a large number of requests are rerouted to the origin server.
-   If your CDN domain is not frequently visited, the corresponding resources may be removed from the cache of the CDN node before they expire.

 |
|[Configure cache rules for resources](reseller.en-US/Best Practices/Optimize the CDN cache hit rates/Configure cache rules for resources.md#)|When the ETag or Last-Modified response headers are not returned, the requested static resource fails to be cached on CDN.|
|[Filter variable parameters in a URL](reseller.en-US/Best Practices/Optimize the CDN cache hit rates/Filter variable parameters in a URL.md#)|When the URL of a request includes a query string or other variable parameters, the requested resource needs to be retrieved from the origin server.|

