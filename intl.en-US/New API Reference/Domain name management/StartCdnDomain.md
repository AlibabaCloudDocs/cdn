# StartCdnDomain

Enables a disabled domain name. After the domain name is enabled, the value of the DomainStatus parameter is changed to Online.

**When you call this operation, note that:**

-   If the domain name is in an invalid state or your have an overdue payment in your account, the domain name cannot be enabled.
-   The maximum number of times that each user can call this operation per second is 100.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=StartCdnDomain&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|StartCdnDomain|The operation that you want to perform. Set the value to **StartCdnDomain**. |
|DomainName|String|Yes|www.yourdomain.com|The domain name that you want to enable. You can specify only one domain name. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|The ID of the request. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com?Action=StartCdnDomain
&DomainName=example.com
&<Common request parameters>
```

Sample success responses

`XML` format

```
<StartCdnDomainResponse>
	  <RequestId>0AEDAF20-4DDF-4165-8750-47FF9C1929C9</RequestId>
</StartCdnDomainResponse>
```

`JSON` format

```
{ "RequestId": "0AEDAF20-4DDF-4165-8750-47FF9C1929C9" }
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

