# BatchStopCdnDomain

Disables one or more accelerated domain names at a time. After an accelerated domain name is disabled, the value of the DomainStatus parameter is changed to Offline.

**When you call this operation, note that:**

-   After an accelerated domain name is disabled, Alibaba Cloud Content Delivery Network \(CDN\) retains the information about the accelerated domain name and automatically redirects requests to the origin server.
-   If you need to temporary disable CDN acceleration for a domain name, we recommend that you call the StopDomain operation.
-   The maximum number of times that each user can call this operation per second is 30.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=BatchStopCdnDomain&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|BatchStopCdnDomain|The operation that you want to perform. Set the value to **BatchStopCdnDomain**. |
|DomainNames|String|Yes|example.com|The accelerated domain names that you want to disable. Separate multiple domain names with commas \(,\). |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|324AEFFF-308C-4DA7-8CD3-01B277B98F28|The ID of the request. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com?Action=BatchStopCdnDomain
&DomainNames=example.com
&<Common request parameters>
```

Sample success responses

`XML` format

```
<BatchStopCdnDomainResponse>
	  <RequestId>324AEFFF-308C-4DA7-8CD3-01B277B98F28</RequestId>
</BatchStopCdnDomainResponse>
```

`JSON` format

```
{
  "RequestId": "324AEFFF-308C-4DA7-8CD3-01B277B98F28"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

