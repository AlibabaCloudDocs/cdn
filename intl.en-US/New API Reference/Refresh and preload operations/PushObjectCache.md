# PushObjectCache

Prefetches content from origin servers to L2 nodes of Alibaba Cloud Content Delivery Network \(CDN\). This reduces workloads on origin servers because users can directly hit cache upon their first visits.

When you call this operation, note that:

-   Alibaba Cloud CDN supports POST requests in which parameters are sent as a form.
-   You can call the RefreshObjectCaches operation to refresh content and call the PushObjectCache operation to prefetch content.
-   You can prefetch content from a maximum of 500 URLs each day.
-   You can upload content from up to 100 URLs per request.
-   A maximum of 50 requests can be submitted per second.
-   Under each account, the prefetch queue can contain up to 100 prefetch requests. Content is prefetched based on the time when the prefetch requests are submitted. The request that is submitted the earliest has the highest priority to prefetch content. If the number of prefetch requests in the queue reaches 100, you can not submit more prefetch requests until the number drops below 100.
-   L2 CDN nodes are deployed between L1 CDN nodes and origin servers to reduce workloads on the origin servers.
-   The maximum number of times that each user can call this operation per second is 50.

**Note:** For more information about how to automate refresh or prefetch tasks, see [Prefetch and refresh task scripts](~~151829~~).

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=PushObjectCache&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|PushObjectCache|The operation that you want to perform. Set the value to **PushObjectCache**. |
|ObjectPath|String|Yes|abc.com/image/1.png\\nabc.com/image/2.png|The URLs from which content is prefetched. Format: **accelerated domain name/files to be prefetched**.

Separate multiple URLs with line feed characters \(\\n\) or a pair of carriage return and line feed characters \(\\r\\n\). |
|Area|String|No|domestic|The accelerated region where content is to be prefetched. Valid values:

-   **domestic**: mainland China.
-   **overseas**: global \(excluding mainland China\).
-   If you do not set this parameter, content in the global \(excluding mainland China\) region is prefetched. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|PushTaskId|String|9524xxxx|The IDs of the prefetch tasks. Multiple task IDs are separated with commas \(,\). |
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|The ID of the request. |

## Examples

Sample requests

```
http(s)://cdn.aliyuncs.com/? Action=PushObjectCache
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

