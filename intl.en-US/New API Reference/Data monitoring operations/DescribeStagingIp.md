# DescribeStagingIp

You can call this operation to query valid virtual IP addresses in the staging environment.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeStagingIp&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeStagingIp|The operation that you want to perform. Set the value to **DescribeStagingIp**. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|IPV4s|List|"IPV4s":\{ "IPV4":\["xx.xx.xx.xx","xx.xx.xx.xx","xx.xx.xx.xx"\] \}|IPv4 addresses. |
|RequestId|String|1B9E0E83-24AC-49F4-9EE0-BF5EB03E8381|The ID of the request. |

## Examples

Sample requests

```
https://cdn.aliyuncs.com/?Action=DescribeStagingIp
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeStagingIpResponse>
  <IPV4s>
        <IPV4>xx.xx.xx.xx</IPV4>
        <IPV4>xx.xx.xx.xx</IPV4>
        <IPV4>xx.xx.xx.xx</IPV4>
  </IPV4s>
  <RequestId>1B9E0E83-24AC-49F4-9EE0-BF5EB03E8381</RequestId>
</DescribeStagingIpResponse>
```

`JSON` format

```
{
     "IPV4s":{
          "IPV4":["xx.xx.xx.xx","xx.xx.xx.xx","xx.xx.xx.xx"]
              },
      "RequestId":"1B9E0E83-24AC-49F4-9EE0-BF5EB03E8381"
   }
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

