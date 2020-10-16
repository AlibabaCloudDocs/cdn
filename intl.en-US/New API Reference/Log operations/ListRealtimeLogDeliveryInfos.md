# ListRealtimeLogDeliveryInfos

Queries the information about real-time log delivery in a specified region.

The maximum number of times that each user can call this operation per second is 100.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=ListRealtimeLogDeliveryInfos&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|ListRealtimeLogDeliveryInfos|The operation that you want to perform. Set the value to **ListRealtimeLogDeliveryInfos**. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Content|Array of RealtimeLogDeliveryInfos| |The content of the log entry. |
|RealtimeLogDeliveryInfos| | | |
|Logstore|String|LogstoreName|The name of the Logstore that collects log data from Alibaba Cloud Content Delivery Network \(CDN\) in real time. |
|Project|String|ProjectName|The name of the Log Service project that is used for real-time log delivery. |
|Region|String|ch-shanghai|The ID of the region where the Log Service project is deployed. For more information, see [Regions that support real-time log delivery](~~144883~~). |
|RequestId|String|95D5B69F-8AEC-419B-8F3A-612B35032B0D|The ID of the request. |

## Examples

Sample requests

```
http(s)://cdn.aliyuncs.com/? Action=ListRealtimeLogDeliveryInfos
&<Common request parameters>
```

Sample success responses

`XML` format

```
<ListRealtimeLogDeliveryInfosResponse>
      <Content>
            <RealtimeLogDeliveryInfos>
                  <Project>test</Project>
                  <Logstore>test</Logstore>
                  <Region>cn-shanghai</Region>
            </RealtimeLogDeliveryInfos>
            <RealtimeLogDeliveryInfos>
                  <Project>test1</Project>
                  <Logstore>test2</Logstore>
                  <Region>cn-shanghai</Region>
            </RealtimeLogDeliveryInfos>
      </Content>
      <RequestId>95D5B69F-8AEC-419B-8F3A-612B35032B0D</RequestId>
</ListRealtimeLogDeliveryInfosResponse>
```

`JSON` format

```
{
    "Content":{
        "RealtimeLogDeliveryInfos":[
            {   
                "Project":"test",
                "Logstore":"test",
                "Region":"cn-shanghai"
            },
            {   
                "Project":"test1",
                "Logstore":"test2",
                "Region":"cn-shanghai"
            }
        ]
    },
    "RequestId":"95D5B69F-8AEC-419B-8F3A-612B35032B0D"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

