# BatchUpdateCdnDomain

Updates the configurations of multiple accelerated domain names at a time.

The maximum number of times that each user can call this operation per second is 30.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=BatchUpdateCdnDomain&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description |
|---------|----|--------|-------|------------|
|Action|String|Yes|BatchUpdateCdnDomain|The operation that you want to perform. Set the value to **BatchUpdateCdnDomain**. |
|DomainName|String|Yes|example.com|The accelerated domain names. You can specify one or more accelerated domain names. Separate multiple domain names with commas \(,\). |
|Sources|String|No|\[\{"content":"1.1.1.1","type":"ipaddr","priority":"20","port":80,"weight":"15"\}\]|The information about the origin server. |
|ResourceGroupId|String|No|abc|The ID of the resource group. |
|TopLevelDomain|String|No|example.com|The top-level domain name. |

The following table lists the descriptions of fields in the Sources parameters.

|Field

|Type

|Required

|Description |
|-------|------|----------|-------------|
|type

|String

|Yes

|The type of the origin server. Valid values:

 ipaddr: The origin server uses an IP address.

 domain: The origin server uses a domain name.

 oss: The origin server is an Object Storage Service \(OSS\) bucket.

 fc\_domain: The origin server uses a Function Compute domain name |
|content

|String

|Yes

|The address of the origin server. You can specify either an IP address or a domain name. |
|port

|Integer

|No

|The port number. You can specify port 443, port 80, or a custom port. Default value: 80. If you specify port 443, Alibaba Cloud CDN will communicate with the origin server over HTTPS. |
|priority

|String

|No

|The priority of the origin server if multiple origin servers are specified. Valid values: 20 and 30. Default value: 20. A value of 20 specifies that the origin server is the primary origin server. A value of 30 specifies that the origin server is a secondary origin. |
|weight

|String

|No

|The weight of the origin server if multiple origin servers are specified. You must specify a value less than 100. Default value: 10. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|15C66C7B-671A-4297-9187-2C4477247A74|The ID of the request. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com?Action=BatchUpdateCdnDomain
&DomainName=example.com,example1.com
&Sources=[{"content":"1.1.1.1","type":"ipaddr","priority":"20","port":80}]
&<Common request parameters>
```

Sample success responses

`XML` format

```
<BatchUpdateCdnDomainResponse>	
      <RequestId>15C66C7B-671A-4297-9187-2C4477247A74</RequestId>
</BatchUpdateCdnDomainResponse>
```

`JSON` format

```
{
  "RequestId": "15C66C7B-671A-4297-9187-2C4477247A74"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|InvalidSources.Malformed|Specified Sources is malformed.|The error message returned because the specified Sources parameter is invalid. You can specify up to 20 IP addresses that are separated with commas \(,\) or one domain name. You cannot specify both IP addresses and domain names in the same request.|
|400|EntityNotExists.ResourceGroup|The resource group does not exist.|The error message returned because the specified resource group does not exist.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

