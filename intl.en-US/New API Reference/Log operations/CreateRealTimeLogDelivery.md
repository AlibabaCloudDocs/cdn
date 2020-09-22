# CreateRealTimeLogDelivery

Configures real-time log delivery for specific accelerated domain names.

You can call this operation up to 100 times per second with each account.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=CreateRealTimeLogDelivery&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|CreateRealTimeLogDelivery|The operation that you want to perform. Set the value to **CreateRealtimeLogDelivery**. |
|Domain|String|Yes|example.com|The accelerated domain name for which you want to configure real-time log delivery. You can specify multiple domain names and separate them with commas \(,\). |
|Logstore|String|Yes|Logstore|The name of the Logstore that collects log data from Alibaba Cloud Content Delivery Network \(CDN\) in real time. |
|Project|String|Yes|test|The name of the Log Service project that is used for real-time log delivery. |
|Region|String|Yes|cn-shanghai|The ID of the region where the Log Service project is deployed. For more information, see [Regions that support real-time log delivery](~~144883~~). |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|F32C57AA-7BF8-49AE-A2CC-9F42390F5A19|The ID of the request. |

## Examples

Sample requests

```
https://cdn.aliyuncs.com?Action=CreateRealTimeLogDelivery
? Domain=xxx.com
&Project=test
&Logstore=test
&Region=test
&<Common request parameters>
```

Sample success responses

`XML` format

```
<CreateRealTimeLogDeliveryResponse>
	  <RequestId>F32C57AA-7BF8-49AE-A2CC-9F42390F5A19</RequestId>
</CreateRealTimeLogDeliveryResponse>
```

`JSON` format

```
{
    "RequestId": "F32C57AA-7BF8-49AE-A2CC-9F42390F5A19"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

