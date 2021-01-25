# DeleteCdnDomain

Deletes an accelerated domain name from Alibaba Cloud Content Delivery Network \(CDN\).

**Note:**

-   We recommend that you add an A record for the domain name in the system of your DNS service provider before you delete the domain name from Alibaba Cloud CDN. Otherwise, the domain name may become inaccessible. Proceed with caution.
-   After you successfully call the DeleteCdnDomain operation, all records of the deleted domain name are removed. If you need to only disable the domain name, we recommend that you call the StopCdnDomain operation.
-   The maximum number of times that each user can call this operation per second is 10.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DeleteCdnDomain&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DeleteCdnDomain|The operation that you want to perform. Set the value to **DeleteCdnDomain**. |
|DomainName|String|Yes|example.com|The accelerated domain name that you want to delete. You can specify only one domain name in each call. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|The ID of the request. |

## Examples

Sample requests

```
http(s)://cdn.aliyuncs.com/? Action=DeleteCdnDomain
&DomainName=example.com
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DeleteCdnDomainResponse>	
      <RequestId>16A96B9A-F203-4EC5-8E43-CB92E68F4CD8</RequestId>
</DeleteCdnDomainResponse>
```

`JSON` format

```
{ "RequestId": "16A96B9A-F203-4EC5-8E43-CB92E68F4CD8" }
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|403|OperationDenied|You do not have access to this operation.|The error code returned because you do not have the permissions to perform the specified operation. You can check your permissions in the Resource Access Management \(RAM\) console.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

