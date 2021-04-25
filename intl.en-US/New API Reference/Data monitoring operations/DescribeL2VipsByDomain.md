# DescribeL2VipsByDomain

Queries the virtual IP addresses of L2 Content Delivery Network \(CDN\) nodes for a specific domain name.

This operation is available to only users whose daily peak bandwidth is higher than 1 Gbit/s. If you meet this requirement, you can [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex) to apply for permissions to use this operation.

The maximum number of time that each user can call this operation per second is 40.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeL2VipsByDomain&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeL2VipsByDomain|The operation that you want to perform. Set the value to **DescribeL2VipsByDomain**. |
|DomainName|String|Yes|www.yourdomain.com|The accelerated domain name. You can specify only one domain name. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|DomainName|String|xxxx.com|The accelerated domain name. |
|Vips|List|"Vip": \[ "1.1.1.1/25", "2.2.2.2/25" \]|A list of virtual IP addresses of L2 CDN nodes. |
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|The ID of the request. |

## Examples

Sample requests

```
https://cdn.aliyuncs.com/?Action=DescribeL2VipsByDomain
&DomainName=example.com
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeL2VipsByDomainResponse>
      <Vips>
            <Vip>xxx.111.111/25</Vip>
            <Vip>xxx.112.112/25</Vip>
            <Vip>xxx.33.190/25</Vip>
            <Vip>xxx.96.109/25</Vip>
            <Vip>xxx.20.226/25</Vip>
            <Vip>xxx.19.140/25</Vip>
            <Vip>xxx.215.140/25</Vip>
      </Vips>
      <RequestId>820E7900-5CA9-4AEF-B0DD-20ED5F64BE55</RequestId>
      <DomainName>example.com</DomainName>
</DescribeL2VipsByDomainResponse>
```

`JSON` format

```
{
  "Vips": {
    "Vip": [
      "xxx.111.111/25",
      "xxx.112.112/25",
      "xxx.33.190/25",
      "xxx.96.109/25",
      "xxx.20.226/25",
      "xxx.19.140/25",
      "xxx.215.140/25"
    ]
  },
  "RequestId": "820E7900-5CA9-4AEF-B0DD-20ED5F64BE55",
  "DomainName": "example.com"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|MissingParameter|The specified value of parameter "DomainName" can not be empty.|The error message returned because the DomainName parameter is not set.|
|400|IllegalOperation|Illegal domain operate is not permitted.|The error message returned because the specified operation is invalid.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

