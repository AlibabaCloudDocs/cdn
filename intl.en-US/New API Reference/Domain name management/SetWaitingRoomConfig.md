# SetWaitingRoomConfig

Configures the virtual waiting room feature for an accelerated domain name. This operation is available only for accelerated domain names of the DCDN workload type.

The maximum number of times that each user can call this operation per second is 30.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=SetWaitingRoomConfig&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|SetWaitingRoomConfig|The operation that you want to perform. Set the value to **SetWaitingRoomConfig**. |
|AllowPct|Integer|Yes|30|The percentage of requests that are allowed to be redirected to the origin server. Valid values: **0** to **100**. |
|DomainName|String|Yes|example.com|The accelerated domain name. You can specify only one domain name. |
|GapTime|Integer|Yes|20|The length of waiting time to skip after users exit the queue. Unit: seconds. |
|MaxTimeWait|Integer|Yes|30|The maximum length of time that users need to wait in the queue. Unit: seconds. |
|WaitUri|String|Yes|xxx|The regular expression that is used to match URI strings for which the virtual waiting room feature is enabled. |
|WaitUrl|String|Yes|WaitUrl|The URL of the waiting page. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|04F0F334-1335-436C-A1D7-6C044FE73368|The ID of the request. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com/?Action=SetWaitingRoomConfig
&DomainName=xxx
&WaitUri=xxx
&AllowPct=30
MaxTimeWait=20
&GapTime=30
&WaitUrl=xxx
&<Common request parameters>
```

Sample success responses

`XML` format

```
<SetWaitingRoomConfigResponse>
      <RequestId>AED00EC1-32A8-4D48-BEB9-BD782AF3C6BD</RequestId>
</SetWaitingRoomConfigResponse>
```

`JSON` format

```
{
    "RequestId": "04F0F334-1335-436C-A1D7-6C044FE73368"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

