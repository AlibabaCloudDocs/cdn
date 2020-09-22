# DescribeIpInfo

Checks whether a specified IP address is assigned to an Alibaba Cloud Content Delivery Network \(CDN\) node.

You can call this operation up to 50 times per second with each account.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeIpInfo&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeIpInfo|The operation that you want to perform. Set the value to **DescribeIpInfo**. |
|IP|String|Yes|1.2.3.4|The IP address to that you want to check. Only one IP address is supported in each call. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|123847FA-9A00-4426-83B8-B4B45D475930|The ID of the request. |
|CdnIp|String|True|Indicates whether the specified IP address is assigned to an Alibaba Cloud CDN node.

 -   **True**: Yes
-   **False**: No |
|ISP|String|China Telecom|The name of the Internet service provider \(ISP\). |
|Region|String|China-Guizhou-Guiyang|The Chinese name of the region. |
|IspEname|String|telecom|The English name of the ISP. |
|RegionEname|String|China-Guizhou-guiyang|The English name of the region. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com/?Action=DescribeIpInfo
&IP=1.2.3.4
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeIpInfoResponse>
  <RegionEname>China-Guizhou-guiyang</RegionEname>
  <Region>China-Guizhou-Guiyang</Region>
  <IspEname>telecom</IspEname>
  <RequestId>1B1D0EE7-9559-489D-BC4E-279495EB8FB8</RequestId>
  <ISP>China Telecom</ISP>
  <CdnIp>True</CdnIp>
</DescribeIpInfoResponse>
```

`JSON` format

```
{
    "RegionEname": "China-Guizhou-guiyang",
    "Region": "China-Guizhou-Guiyang",
    "IspEname": "telecom",
    "RequestId": "1B1D0EE7-9559-489D-BC4E-279495EB8FB8",
    "ISP": "China Telecom",
    "CdnIp": "True"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|InvalidIP.ValueNotSupported|The specified value of parameter IP is not supported.|The error message returned because the specified IP parameter is not supported. Modify the value of the IP parameter and try again.|
|400|MissingParameter|The specified value of parameter "IP" is not valid.|The error message returned because the specified IP parameter is invalid.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

