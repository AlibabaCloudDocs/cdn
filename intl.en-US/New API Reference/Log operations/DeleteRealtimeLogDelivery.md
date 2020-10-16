# DeleteRealtimeLogDelivery

Deletes the configurations of real-time log delivery for specified accelerated domain names.

The maximum number of times that each user can call this operation per second is 100.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DeleteRealtimeLogDelivery&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DeleteRealtimeLogDelivery|The operation that you want to perform. Set the value to **DeleteRealtimeLogDelivery**. |
|Domain|String|Yes|example.com|The acceleration domain name for which you want to disable real-time log delivery. You can specify multiple domain names and separate them with commas \(,\). |
|Logstore|String|Yes|LogstoreName|The name of the Logstore that collects log data from Alibaba Cloud Content Delivery Network \(CDN\) in real time. |
|Project|String|Yes|ProjectName|The name of the Log Service project that is used for real-time log delivery. |
|Region|String|Yes|cn-shanghai|The ID of the region where the Log Service project is deployed. For more information, see [Regions that support real-time log delivery](~~144883~~). |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|9732E117-8A37-49FD-A36F-ABBB87556CA7|The ID of the request. |

## Examples

Sample requests

```
http(s)://cdn.aliyuncs.com/? Action=DeleteRealtimeLogDelivery
&Domain=example.com
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DeleteRealtimeLogDeliveryResponse>
	  <RequestId>9732E117-8A37-49FD-A36F-ABBB87556CA7</RequestId>
</DeleteRealtimeLogDeliveryResponse>
```

`JSON` format

```
{
    "RequestId": "9732E117-8A37-49FD-A36F-ABBB87556CA7"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

