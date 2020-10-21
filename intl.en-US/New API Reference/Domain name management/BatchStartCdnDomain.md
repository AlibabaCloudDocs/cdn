# BatchStartCdnDomain

Enables one or more domain names at a time. After a domain name is enabled, the value of the DomainStatus parameter is changed to Online.

**When you call this operation, note that:**

-   If the domain name is in an invalid state or your have an overdue payment in your account, the domain name cannot be enabled.
-   The maximum number of times that each user can call this operation per second is 30.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=BatchStartCdnDomain&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|BatchStartCdnDomain|The operation that you want to perform. Set the value to **BatchStartCdnDomain**. |
|DomainNames|String|Yes|example.com|The domain names that you want to enable. Separate multiple domain names with commas \(,\). |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|0AEDAF20-4DDF-4165-8750-47FF9C1929C9|The ID of the request. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com/?Action=BatchStartCdnDomain
&DomainNames=example.com
&<Common request parameters>
```

Sample success responses

`XML` format

```
<BatchStartCdnDomainResponse>
	  <RequestId>0AEDAF20-4DDF-4165-8750-47FF9C1929C9</RequestId>
</BatchStartCdnDomainResponse>
```

`JSON` format

```
{
  "RequestId": "0AEDAF20-4DDF-4165-8750-47FF9C1929C9"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

