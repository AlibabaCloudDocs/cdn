# DescribeCdnService

Queries the status of Alibaba Cloud Content Delivery Network \(CDN\) for your account. The status information includes the service activation time, current service status, current billing method, and new billing method.

You can call this operation up to 30 times per second with each account.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeCdnService&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeCdnService|The operation that you want to perform. Set the value to **DescribeCdnService**. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|InternetChargeType|String|PayByTraffic|The current billing method of the service.

-   **PayByTraffic**: pay-by-data-transfer.
-   **PayByBandwidth**: pay-by-bandwidth. |
|OpeningTime|String|2019-02-28T13:11:49Z|The time when the service was activated. The time follows the ISO 8601 standard in the yyyy-MM-ddThh:mmZ format. |
|ChangingChargeType|String|PayByTraffic|The new billing method that Alibaba Cloud CDN will use. Valid values:

-   **PayByTraffic**: pay-by-data-transfer.
-   **PayByBandwidth**: pay-by-bandwidth. |
|ChangingAffectTime|String|2019-11-27T16:00:00Z|The time when the new billing method takes effect. The time is displayed in GMT. |
|OperationLocks|Array| |The lock status of the service. |
|LockReason| | | |
|LockReason|String|financial|The reason why the service is locked. A value of financial indicates that the service is locked due to overdue payments. |
|InstanceId|String|aliuidxx|The ID of the instance. |
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|The ID of the request. |

## Examples

Sample requests

```
https://cdn.aliyuncs.com?&Action=DescribeCdnService
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeCdnServiceResponse>
  <ChangingAffectTime>2014-11-27T16:00:00Z</ChangingAffectTime>
  <ChangingChargeType>PayByBandwidth</ChangingChargeType>
  <InternetChargeType>PayByTraffic</InternetChargeType>
  <OpeningTime>2014-02-28T13:11:49Z</OpeningTime>
  <OperationLocks>
</OperationLocks>
  <InstanceId>aliuidxx</InstanceId>
  <RequestId>BFFCDFAD-DACC-484E-9BE6-0AF3B3A0DD23</RequestId>
</DescribeCdnServiceResponse>
```

`JSON` format

```
{
    "ChangingAffectTime": "2014-11-27T16:00:00Z",
    "ChangingChargeType": "PayByBandwidth",
    "InternetChargeType": "PayByTraffic",
    "OpeningTime": "2014-02-28T13:11:49Z",
    "OperationLocks": {
        "LockReason": []
    },
    "InstanceId":"aliuidxx",
    "RequestId": "BFFCDFAD-DACC-484E-9BE6-0AF3B3A0DD23"
}
```

## Error codes

|HTTP status code|Error code|Error message|Description|
|----------------|----------|-------------|-----------|
|400|UnsupportedParameter|There is unsupported parameters|The error message returned because the specified parameter value is not supported.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

