# DescribeUserVipsByDomain

Queries the virtual IP addresses of Content Delivery Network \(CDN\) nodes by domain name.

The maximum number of times that each user can call this operation per second is 30.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeUserVipsByDomain&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeUserVipsByDomain|The operation that you want to perform. Set the value to DescribeUserVipsByDomain. |
|DomainName|String|Yes|example.com|The accelerated domain name. You can specify only one domain name. |
|Available|String|No|on|Specifies whether you want to query the virtual IP addresses of only healthy CDN nodes. Valid values:

 -   **on**: queries the virtual IP addresses of healthy CDN nodes.
-   **off**: queries the virtual IP addresses of all CDN nodes. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|DomainName|String|example.com|The accelerated domain name. |
|RequestId|String|820E7900-5CA9-4AEF-B0DD-20ED5F64BE55|The ID of the request. |
|Vips|List|122.72.xxx.xxx|The list of virtual IP addresses. |

## Examples

Sample requests

```
https://cdn.aliyuncs.com?Action=DescribeUserVipsByDomain
&Available=on
&DomainName=example.com
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeUserVipsByDomainResponse>
	  <Vips>
		    <Vip>122.72.xxx.xxx</Vip>
		    <Vip>119.14.xxx.xxx</Vip>
		    <Vip>221.13.xxx.xxx</Vip>
		    <Vip>124.95.xxx.xxx</Vip>
		    <Vip>58.211.xxx.xxx</Vip>
	  </Vips>
	  <RequestId>820E7900-5CA9-4AEF-B0DD-20ED5F64BE55</RequestId>
	  <DomainName>example.com</DomainName>
</DescribeUserVipsByDomainResponse>
```

`JSON` format

```
{
  "Vips": {
    "Vip": [
      "122.72.xxx.xxx",
      "119.14.xxx.xxx",
      "221.13.xxx.xxx",
      "124.95.xxx.xxx",
      "58.211.xxx.xxx"
    ]
  },
  "RequestId": "820E7900-5CA9-4AEF-B0DD-20ED5F64BE55",
  "DomainName": "example.com"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|MissingParameter|The specified value of parameter "DomainName" can not be empty.|The error message returned because the DomainName parameter is not specified.|
|400|IllegalOperation|Illegal domain operate is not permitted.|The error message returned because the specified operation is invalid.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

