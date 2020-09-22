# BatchAddCdnDomain

Adds multiple domain names to Alibaba Cloud Content Delivery Network \(CDN\) at a time. You can add a maximum of 20 domain names to Alibaba Cloud CDN under each account.

**When you call this operation, note that:**

-   You can add a maximum of 20 domain names to Alibaba Cloud CDN under each account.
-   Before you add a domain name to Alibaba Cloud, you must activate Alibaba Cloud CDN. For more information, see [Activate Alibaba Cloud CDN](~~27272~~).
-   Make sure that you have obtained an Internet content provider \(ICP\) number for the domain name that you want to add.
-   If the content from the origin server is not stored on Alibaba Cloud, the content must be reviewed by Alibaba Cloud. The review will be completed by the end of the next business day after you submit the application.
-   The maximum number of times that each user can call this operation per second is 30.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=BatchAddCdnDomain&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|BatchAddCdnDomain|The operation that you want to perform. Set this parameter to **BatchAddCdnDomain**. |
|CdnType|String|Yes|web|The workload type of the accelerated domain name. Valid values:

 -   **web**: images and small files.
-   **download**: downloads of large files.
-   **video**: on-demand video and audio streaming. |
|DomainName|String|Yes|example1.com,example2.com|The domain names that you want to add to Alibaba Cloud CDN. Separate multiple domain names with commas \(,\). |
|Sources|String|Yes|\[\{"content":"1.1.1.1","type":"ipaddr","priority":"20","port":80,"weight":"15"\}\]|The information about the origin server. |
|ResourceGroupId|String|No|123|The ID of the resource group. If you do not specify this parameter, the system automatically uses the ID of the default resource group. |
|CheckUrl|String|No|url|The URL that is used to test the accessibility of the origin server. |
|Scope|String|No|domestic|Valid values:

 -   **domestic**: mainland China.
-   **overseas**: global \(excluding mainland China\).
-   **global**: global. |
|TopLevelDomain|String|No|www.yourdomain.com|The top-level domain name. |

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

 ipaddr: The origin server uses an IP address

 domain: The origin server uses a domain name.

 oss: The origin server uses an Object Storage Service \(OSS\) bucket.

 fc\_domain: The origin server uses a Function Compute domain name. |
|content

|String

|Yes

|The address of the origin server. You can specify either an IP address or a domain name. |
|port

|Integer

|No

|You can specify port 443, port 80, or a custom port. Default value: 80. If you specify port 443, Alibaba Cloud will communicate with the origin server over HTTPS. |
|priority

|String

|No

|The priority of the origin server if multiple origin servers are specified. Valid values: 20 and 30. Default value: 20. A value of 20 specifies that the origin server is the primary origin. A value of 30 specifies that the origin server is a secondary origin. |
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
http(s)://cdn.aliyuncs.com/? Action=BatchAddCdnDomain
&CdnType=web
&DomainName=example1.com,example2.com
&Sources=[{"content":"1.1.1.1","type":"ipaddr","priority":"20","port":80,"weight":"15"}]
&<Common request parameters>
```

Sample success responses

`XML` format

```
<BatchAddCdnDomainResponse>
	  <RequestId>15C66C7B-671A-4297-9187-2C4477247A74</RequestId>
</BatchAddCdnDomainResponse>
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
|400|InvalidDomainName.Malformed|Specified DomainName is malformed.|The error message returned because the format of the specified domain names is invalid or wildcard domain names are not supported.|
|400|MissingParameter|The input parameter cdnType that is mandatory for processing this request is not supplied.|The error message returned because the CdnType parameter must be set.|
|400|InvalidCdnType.Malformed|Specified CdnType is malformed.|The error message returned because the specified CdnType parameter is invalid. Valid values: web, download, video, and liveStream.|
|400|InvalidSources.Malformed|Specified Sources is malformed.|The error message returned because the format of the specified Sources parameter is invalid. You can specify up to 20 IP addresses that are separated with commas \(,\) or one domain name. You cannot specify both IP addresses and domain names in one request.|
|400|MissingParameter|The input parameter sourceType that is mandatory for processing this request is not supplied.|The error message returned because the SourceType parameter must be set.|
|400|InvalidSourceType.Malformed|Specified CdnType is malformed.|The error message returned because the format of the CdnType parameter is invalid.|
|400|InvalidScope.Malformed|Specified Scope is malformed.|The error message returned because the format of the Scope parameter is invalid.|
|400|SourceIp.Exceed|The Certificate you provided is malformed!|The error message returned because the format of the SSL certificate is invalid.|
|400|InvalidCertificate|The Certificate you provided is malformed!|The error message returned because the format of the SSL certificate is invalid.|
|400|InvalidCertificate.TooLong|The Certificate you provided is over the max length!|The error message returned because the length of the specified certificate and private key exceeds the upper limit.|
|400|InnerAddDomainDenied|Your account haven't bind aoneId, can not add domain.|The error message returned because you cannot add a domain name by using an account that is not associated with an Aone ID.|
|400|ExtensiveAndAllBothExist|Extensive domain and the domain begins with 'all.' can not exist at the same time.|The error message returned because wildcard domain names and domain names starting with the string "all." cannot exist at the same time .|
|400|CdnTypeNotSupportExtensiveDomain|Extensive domain not supported for this cdn type.|The error message returned because wildcard domains do not support the specified workload type. Wildcard domains only support the following workload types: web, download, and video.|
|400|ExtensiveAndSpecificDomainConflict|Extensive domain and corresponding specific domain are mutually exclusive.|The error message returned because the specified wildcard domain name matches an existing domain name at the same level. Wildcard domain names are mutually exclusive with specific domain names.|
|400|InvalidResourceGroupId.Malformed|Specified ResourceGroupId is malformed.|The error message returned because the format of the ResourceGroupId parameter is invalid.|
|400|InvalidDomainNameLevel|Domain name suffixed with alicdn.com only support third level.|The error message returned because the specified domain name is not supported. Alibaba Cloud CDN supports up to three levels of domain names.|
|400|InvalidTopLevelDomain.Malformed|Specified TopLevelDomain is malformed.|The error message returned because the specified TopLevelDomain parameter is invalid.|
|400|TopLevelDomain.NotFound|TopLevelDomain is not exist.|The error message returned because the specified TopLevelDomain parameter does not exist.|
|400|EntityNotExists.ResourceGroup|The resource group does not exist.|The error message returned because the specified resource group does not exist.|
|400|InvalidStatus.ResourceGroup|It's now allowed to do this operation because of the current status of resource-group.|The error message returned because the operation is not allowed when the resource group is in the current state.|
|400|NotInternationRealIdentity|You need to do real name authentication when you use Chinese mainland resources.|The error message returned because you have not completed real-name verification that is required to use resources in mainland China.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

