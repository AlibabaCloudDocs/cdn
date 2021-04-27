# PushObjectCache

Prefetches content from origin servers to L2 nodes of Alibaba Cloud Content Delivery Network \(CDN\). This reduces loads on origin servers because users can directly hit cache upon their first visits.

**Note:**

-   Alibaba Cloud CDN supports POST requests in which parameters are sent as a form.
-   You can call the RefreshObjectCaches operation to refresh content and call the PushObjectCache operation to prefetch content.
-   You can specify at most 100 URLs in each prefetch request. You can submit at most 500 URLs every day by using each Alibaba Cloud account. If the daily peak bandwidth value exceeds 500 Mbit/s, you can [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex) to request a quota increase. Alibaba Cloud CDN evaluates your application based on your workloads.
-   For each Alibaba Cloud account, the prefetch queue can contain up to 100 prefetch requests. Content is prefetched in order of the time when the prefetch requests are submitted. The request that is submitted the earliest has the highest priority to prefetch content. If the number of prefetch requests in the queue reaches 100, you cannot submit more prefetch requests until the number drops below 100.
-   L2 CDN nodes are deployed between L1 CDN nodes and origin servers to reduce loads on the origin servers.
-   The maximum number of times that each user can call this operation per second is 50.
-   For more information about how to automate refresh or prefetch tasks, see [Prefetch and refresh task scripts](~~151829~~).

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=PushObjectCache&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|PushObjectCache|The operation that you want to perform. Set the value to **PushObjectCache**. |
|ObjectPath|String|Yes|abc.com/image/1.png\\nabc.com/image/2.png|The URLs from which content is prefetched. Format: **accelerated domain name/files to be prefetched**.

 The URLs to be refreshed. You can specify multiple URLs and separate them with line feed characters \(\\n or \\r\\n\). |
|Area|String|No|domestic|The accelerated region where content is to be prefetched. Valid values:

 -   **domestic**: accelerated regions in mainland China.
-   **overseas**: accelerated regions outside mainland China.

 If you do not set this parameter, content in the accelerated region of the accelerated domain name is prefetched. The rules are:

 -   If the accelerated region is set to Mainland China Only, content in regions in mainland China is prefetched.
-   If the accelerated region is set to Global, content in all regions is prefetched.
-   If the accelerated region is set to Global \(Excluding Mainland China\), content in regions outside mainland China is prefetched. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|PushTaskId|String|9524xxxx|The ID of the refresh task. If multiple tasks are returned, the IDs are separated with commas \(,\). |
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|The ID of the request. |

## Examples

Sample requests

```
http(s)://cdn.aliyuncs.com/?Action=PushObjectCache
&ObjectPath=abc.com/image/1.png\nabc.com/image/2.png
&<Common request parameters>
```

Sample success responses

`XML` format

```
<PushObjectCacheResponse>
    <PushTaskId>9524xxxx</PushTaskId>
    <RequestId>16A96B9A-F203-4EC5-8E43-CB92E68F4CD8</RequestId>
</PushObjectCacheResponse>
```

`JSON` format

```
{
  "PushTaskId": "9524xxxx",
  "RequestId": "16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

