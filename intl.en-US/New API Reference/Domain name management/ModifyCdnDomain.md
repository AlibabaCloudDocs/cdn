# ModifyCdnDomain

Modifies the information about an accelerated domain name.

**Note:** The maximum number of times that each user can call this operation per second is 30.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=ModifyCdnDomain&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|ModifyCdnDomain|The operation that you want to perform. Set the value to **ModifyCdnDomain**. |
|DomainName|String|Yes|example.com|The accelerated domain name. You can specify only one domain name in each call. |
|Sources|String|No|\[\{"content":"1.1.1.1","type":"ipaddr","priority":"20","port":80,"weight":"15"\}\]|The list of origin URLs.

**Note:** You cannot set both the **Sources** and **TopLevelDomain** parameters in the same request. Otherwise, ********the **TopLevelDomain** parameter cannot take effect. |
|ResourceGroupId|String|No|rg-acfmyuji4b6r4\*\*|The ID of the resource group. |
|TopLevelDomain|String|No|your.top.domain.com|The top-level domain name. To add a top-level domain name, set the parameter CDN\_TOP\_LEVEL\_DOMAIN\_GREY\_USER\_LIST. This feature is available to only selected users.

**Note:** You cannot set both the **Sources** and **TopLevelDomain** parameters in the same request. Otherwise, ********the **TopLevelDomain** parameter cannot take effect. |

The following table describes the fields in the Sources parameter.

|Parameter

|Type

|Required

|Description |
|-----------|------|----------|-------------|
|type

|String

|Yes

|The type of origin server. Valid values:

ipaddr: The origin server uses an IP address.

domain: The origin server uses a domain name.

oss: The origin server is an Object Storage Service \(OSS\) bucket.

fc\_domain: The origin server uses a Function Compute domain name. |
|content

|String

|Yes

|The origin address. You can specify either an IP address or a domain name. |
|port

|Integer

|No

|The port number. You can specify port 80, port 443, or a custom port. Default value: 80. If you specify port 443, Alibaba Cloud Content Delivery Network \(CDN\) communicates with the origin server over HTTPS. |
|priority

|String

|No

|The priority of the origin server if multiple origin servers are specified. Valid values: 20 and 30. Default value: 20. A value of 20 specifies that the origin server is the primary origin server. A value of 30 specifies that the origin server is a secondary origin server. |
|weight

|String

|No

|The weight of the origin server if multiple origin servers are specified. You must specify a value less than 100. Default value: 10. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|The ID of the request. |

## Examples

Sample requests

```
http(s)://cdn.aliyuncs.com/? Action=ModifyCdnDomain
&SourceType=domain
&DomainName=example.com
&Sources=[{"content":"1.1.1.1","type":"ipaddr","priority":"20","port":80,"weight":"15"}]
&<Common request parameters>
```

Sample success responses

`XML` format

```
<ModifyCdnDomainResponse>
      <RequestId>94E3559F-7B6A-4A5E-AFFD-44E2A208A249</RequestId>
</ModifyCdnDomainResponse>
```

`JSON` format

```
{ "RequestId": "94E3559F-7B6A-4A5E-AFFD-44E2A208A249" }
```

## Error codes

|HTTP status code|Error code|Error message|Description|
|----------------|----------|-------------|-----------|
|400|EntityNotExists.ResourceGroup|The resource group does not exist.|The error message returned because the specified resource group does not exist.|
|400|TopLevelDomain.NotFound|TopLevelDomain is not exist.|The error message returned because the specified value of the TopLevelDomain parameter does not exist.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

