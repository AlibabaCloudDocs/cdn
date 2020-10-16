# ListDomainsByLogConfigId

Queries all accelerated domain names associated with a custom log configuration.

The maximum number of times that each user can call this operation per second is 100.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=ListDomainsByLogConfigId&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|ListDomainsByLogConfigId|The operation that you want to perform. Set the value to **ListDomainsByLogConfigId**. |
|ConfigId|String|Yes|123|The ID of the custom configuration. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Domains|List|\[ "abc.com", "a.b.c.com" \]|The list of domain names. |
|RequestId|String|94E3559F-7B6A-4A5E-AFFD-44E2A208A249|The ID of the request. |

## Examples

Sample requests

```
http(s)://cdn.aliyuncs.com/? Action=ListDomainsByLogConfigId
&ConfigId=123
&<Common request parameters>
```

Sample success responses

`XML` format

```
<ListDomainsByLogConfigIdResponse>
	  <RequestId>9732E117-8A37-49FD-A36F-ABBB87556CA7</RequestId>
	  <Domains>
		    <Domain>abc.com</Domain>
		    <Domain>a.b.c.com</Domain>
	  </Domains>
</ListDomainsByLogConfigIdResponse>
```

`JSON` format

```
{ "RequestId": "9732E117-8A37-49FD-A36F-ABBB87556CA7", "Domains": { "Domain": [ "abc.com", "a.b.c.com" ] } }
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

