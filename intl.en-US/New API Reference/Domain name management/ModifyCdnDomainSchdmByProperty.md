# ModifyCdnDomainSchdmByProperty

Modifies the accelerated region for an accelerated domain name.

The maximum number of times that each user can call this operation per second is 100.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=ModifyCdnDomainSchdmByProperty&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|ModifyCdnDomainSchdmByProperty|The operation that you want to perform. Set the value to **ModifyCdnDomainSchdmByProperty**. |
|DomainName|String|Yes|example.com|The accelerated domain name. You can specify only one domain name. |
|Property|String|Yes|\{"coverage":"overseas"\}|The name of the accelerated region. Valid values:

 -   **domestic**: mainland China only. This is the default value.
-   **overseas**: global \(excluding mainland China\).
-   **global**: global. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|15C66C7B-671A-4297-9187-2C4477247A74|The ID of the request. |

## Examples

Sample requests

```
http(s)://cdn.aliyuncs.com/? Action=ModifyCdnDomainSchdmByProperty
&DomainName=example.com
&Property={"coverage":"overseas"}
&<Common request parameters>
```

Sample success responses

`XML` format

```
<ModifyCdnDomainSchdmByPropertyResponse>
	  <RequestId>15C66C7B-671A-4297-9187-2C4477247A74</RequestId>
</ModifyCdnDomainSchdmByPropertyResponse>
```

`JSON` format

```
{
  "RequestId": "15C66C7B-671A-4297-9187-2C4477247A74"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

