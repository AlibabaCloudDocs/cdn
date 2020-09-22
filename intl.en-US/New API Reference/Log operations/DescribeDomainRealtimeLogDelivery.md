# DescribeDomainRealtimeLogDelivery

Queries the information about real-time log delivery for an accelerated domain name.

You can call this operation up to 100 times per second with each account.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeDomainRealtimeLogDelivery&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeDomainRealtimeLogDelivery|The operation that you want to perform. Set the value to **DescribeDomainRealtimeLogDelivery**. |
|Domain|String|Yes|example.com|The accelerated domain name for which real-time log delivery is enabled. Only one domain name is supported. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Logstore|String|test|The name of the Logstore that collects log data from Alibaba Cloud Content Delivery Network \(CDN\) in real time. |
|Project|String|test|The name of the Log Service project that is used for real-time log delivery. |
|Region|String|cn-shanghai|The ID of the region where the Log Service project is deployed. |
|RequestId|String|2F8F3852-912F-42AC-80EB-F1CF4284DE93|The ID of the request. |
|Status|String|online|The status of the real-time log delivery feature. |

## Examples

Sample requests

```
https://cdn.aliyuncs.com/?Action=DescribeDomainRealtimeLogDelivery
&Domain=xxx.com
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeDomainRealtimeLogDeliveryResponse>
	  <Project>test</Project>
	  <Logstore>test</Logstore>
	  <Region>cn-shanghai</Region>
	  <Status>online</Status>
	  <RequestId>2F8F3852-912F-42AC-80EB-F1CF4284DE93</RequestId>
</DescribeDomainRealtimeLogDeliveryResponse>
```

`JSON` format

```
{
    "Project":"test",
    "Logstore":"test",
    "Region":"cn-shanghai",
    "Status":"online",
    "RequestId":"2F8F3852-912F-42AC-80EB-F1CF4284DE93"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

