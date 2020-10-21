# StopCdnDomain

Disables a domain name that is accelerated by Alibaba Cloud Content Delivery Network \(CDN\). After the domain name is disabled, the value of the DomainStatus parameter is changed to Offline.

When you call this operation, note that:

-   After an accelerated domain is disabled, the information about the domain name is retained. Requests destined for the domain name are automatically redirected to the origin server.
-   The maximum number of times that each user can call this operation per second is 40.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=StopCdnDomain&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|StopCdnDomain|The operation that you want to perform. Set the value to **StopCdnDomain**. |
|DomainName|String|Yes|www.yourdomain.com|The accelerated domain name that you want to disable. You can specify only one domain name. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|The ID of the request. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com?Action=StopCdnDomain
&DomainName=example.com
&<Common request parameters>
```

Sample success responses

`XML` format

```
<StopCdnDomainResponse>
	  <RequestId>324AEFFF-308C-4DA7-8CD3-01B277B98F28</RequestId>
</StopCdnDomainResponse>
```

`JSON` format

```
{ "RequestId": "324AEFFF-308C-4DA7-8CD3-01B277B98F28" }
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

