# Query details about resource plans

If you have purchased an Alibaba Cloud Content Delivery Network \(CDN\) resource plan, you can query the details about the resource plan. Usage details help you make informed business decisions. This topic describes how to query details about resource plans.

## Prerequisites

-   A resource plan is purchased. For more information, see [CDN Resource Plan](https://common-buy-intl.aliyun.com/?commodityCode=+cdn_bag_intl#/buy).
-   Only CDN resources that use the pay-by-data-transfer metering method can use resource plans.

## Procedure

1.  Log on to the[Alibaba Cloud CDN console](https://cdn.console.aliyun.com).
2.  Click the **Resource Plans** tab.

    You can view the total capacity, remaining capacity, effective time, expiration time, and status of each resource plan.

    ![Resource plans](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2019438951/p51553.png)


## Related API operations

You can call API operations listed in the following table to query details about resource plans.

|API|Description|
|---|-----------|
|[DescribeCdnUserResourcePackage](https://www.alibabacloud.com/help/doc-detail/91171.htm)|Queries the resource plans that you have purchased for Alibaba Cloud CDN.|
|[DescribeDcdnUserResourcePackage](https://www.alibabacloud.com/help/doc-detail/131648.htm)|Queries the resource plans that you have purchased for Dynamic Router for CDN \(DCDN\).|

**Note:** Resource plans of DCDN can be shared between Alibaba Cloud CDN and DCDN. Therefore, you can also call the DCDN API to query details about resource plans of Alibaba Cloud CDN.

