# ModifyCdnService

Changes the billing method of Alibaba Cloud Content Delivery Network \(CDN\).

**When you call this operation, note the following information:**

-   You must activate Alibaba Cloud CDN before you can call this operation.
-   The new billing method takes effect at 00:00 the following day. If you change the billing method several times, the last change takes effect. The following billing methods are supported: pay-by-bandwidth and pay-by-data-transfer.
-   You can call this operation up to 10 times per second with each account.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=ModifyCdnService&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|ModifyCdnService|The operation that you want to perform. Set the value to **ModifyCdnService**. |
|InternetChargeType|String|Yes|PayByTraffic|The new billing method that Alibaba Cloud CDN will use. Valid values:

-   **PayByTraffic**: pay-by-data-transfer.
-   **PayByBandwidth**: pay-by-bandwidth. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|The ID of the request. |

## Examples

Sample requests

```
https://cdn.aliyuncs.com?&Action=ModifyCdnService
&InternetChargeType=PayByTraffic
&<Common request parameters>
```

Sample success responses

`XML` format

```
<ModifyCdnServiceResponse>
    <RequestId>97C68796-EB7F-4D41-9D5B-12B909D76508</RequestId>
</ModifyCdnServiceResponse>
```

`JSON` format

```
{ "RequestId":"97C68796-EB7F-4D41-9D5B-12B909D76508" }
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|InvalidParameter|The specified value of parameter "InternetChargeType" is not valid.|The error message returned because the specified value of the InternetChargeType parameter is invalid.|
|400|InsufficientBalance|Your account does not have enough balance.|The error message returned because your account balance is insufficient. Top up your account and try again.|
|400|FUWU\_BIZ\_COMMODITY\_VERIFY\_FAIL\_INVALID\_PAY\_METHOD|INVALID\_PAY\_METHOD|The error message returned because the specified payment method is invalid.|
|400|FUWU\_BIZ\_COMMODITY\_VERIFY\_FAIL\_HASORDER|You have an order not yet effective|The error message returned because you have pending orders.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

