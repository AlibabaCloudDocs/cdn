# OpenCdnService

Activates Alibaba Cloud Content Delivery Network \(CDN\). You must activate Alibaba Cloud CDN before you can manage domain names in Alibaba Cloud CDN.

**Note:**

-   Alibaba Cloud CDN can be activated only once per Alibaba Cloud account. The Alibaba Cloud account must pass real-name verification.
-   The maximum number of times that each user can call this operation per second is 5.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=OpenCdnService&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|OpenCdnService|The operation that you want to perform. Set the value to **OpenCdnService**. |
|InternetChargeType|String|Yes|PayByTraffic|The metering method of Alibaba Cloud CDN. A value of **PayByTraffic** indicates that the metering method is pay-by-data-transfer. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|97C68796-EB7F-4D41-9D5B-12B909D76508|The ID of the request. |

## Examples

Sample requests

```
http(s)://cdn.aliyuncs.com/? Action=OpenCdnService
&InternetChargeType=PayByTraffic
&<Common request parameters>
```

Sample responses

`XML` format

```
<OpenCdnServiceResponse>
      <RequestId>97C68796-EB7F-4D41-9D5B-12B909D76508</RequestId>
</OpenCdnServiceResponse>
```

`JSON` format

```
{
  "RequestId": "97C68796-EB7F-4D41-9D5B-12B909D76508"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|403|Forbidden.Intl|User not authorized to open Intl service.|The error message returned because Alibaba Cloud CDN is available to only selected users.|
|400|InvalidInternetChargeType.ValueNotSupported|The specified value of parameter "InternetChargeType" is not valid.|The error message returned because the InternetChargeType parameter is set to an invalid value.|
|400|CdnService.HasOpened|Your cdn service has opened.|The error message returned because you have activated Alibaba Cloud CDN. You do not need to activate the service again.|
|400|InsufficientBalance|Your account does not have enough balance.|The error message returned because your Alibaba Cloud account has an insufficient balance. Top up your account and try again.|
|400|NoRealNameAuthentication|Real name authentication is needed.|The error message returned because your Alibaba Cloud account has not passed real-name verification.|
|403|Forbidden.BidUser|Bid user is limited to open service.|The error message returned because you are not authorized to use this service.|
|400|FUWU\_BIZ\_COMMODITY\_VERIFY\_FAIL\_INVALID\_PAY\_METHOD|INVALID\_PAY\_METHOD|The error message returned because the specified payment method is invalid.|
|400|FUWU\_BIZ\_COMMODITY\_VERIFY\_FAIL\_USERPROFILECOMPLETE|MISSING\_USERPROFILE|The error message returned because a required user profile is missing.|
|400|LX\_CREATE\_ORDER\_FAILED|Create order failed|The error message returned because the order failed to be created.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

