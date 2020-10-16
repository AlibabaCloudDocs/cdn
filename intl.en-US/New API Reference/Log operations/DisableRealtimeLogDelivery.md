# DisableRealtimeLogDelivery

Disables real-time log delivery for specified accelerated domain names.

The maximum number of times that each user can call this operation per second is 100.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DisableRealtimeLogDelivery&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DisableRealtimeLogDelivery|The operation that you want to perform. Set the value to **DisableRealtimeLogDelivery**. |
|Domain|String|Yes|example.com|The accelerated domain name for which you want to disable real-time log delivery. You can specify multiple domain names and separate them with commas \(,\). |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|9732E117-8A37-49FD-A36F-ABBB87556CA7|The ID of the request. |

## Examples

Sample requests

```
https://cdn.aliyuncs.com?Action=DisableRealtimeLogDelivery
&Domain=xxx.com
```

Sample success responses

`XML` format

```
<DisableRealtimeLogDeliveryResponse>
	  <RequestId>9732E117-8A37-49FD-A36F-ABBB87556CA7</RequestId>
</DisableRealtimeLogDeliveryResponse>
```

`JSON` format

```
{
    "RequestId": "9732E117-8A37-49FD-A36F-ABBB87556CA7"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

