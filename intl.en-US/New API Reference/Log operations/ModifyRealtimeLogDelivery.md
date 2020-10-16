# ModifyRealtimeLogDelivery

Modifies the configurations of real-time log delivery for a specific domain name. Each domain name supports only one Logstore.

The maximum number of times that each user can call this operation per second is 100.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=ModifyRealtimeLogDelivery&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|ModifyRealtimeLogDelivery|The operation that you want to perform. Set the value to **ModifyRealtimeLogDelivery**. |
|Domain|String|Yes|example.com|The accelerated domain name for which you want to modify the configurations of real-time log delivery. Only one domain name is supported. |
|Project|String|Yes|testProject|The name of the Log Service project that is used for real-time log delivery. |
|Logstore|String|Yes|TestLog|The name of the Logstore. |
|Region|String|Yes|ch-shanghai|The ID of the region where the Log Service project is deployed. For more information, see [Regions that support real-time log delivery](~~144883~~). |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|9732E117-8A37-49FD-A36F-ABBB87556CA7|The ID of the request. |

## Examples

Sample requests

```
https://cdn.aliyuncs.com?Action=ModifyRealtimeLogDelivery
&Domain=xxx.com
&Project=testProject
&Logstore=TestLog
&Region=cn-hangzhou.log.aliyuncs.com
```

Sample success responses

`XML` format

```
<ModifyRealtimeLogDeliveryResponse>
	  <RequestId>9732E117-8A37-49FD-A36F-ABBB87556CA7</RequestId>
</ModifyRealtimeLogDeliveryResponse>
```

`JSON` format

```
{
    "RequestId": "9732E117-8A37-49FD-A36F-ABBB87556CA7"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

