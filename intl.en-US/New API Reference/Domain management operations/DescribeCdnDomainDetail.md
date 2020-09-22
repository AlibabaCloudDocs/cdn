# DescribeCdnDomainDetail

Queries the basic information about an accelerated domain name.

The maximum number of times that each user can call this operation per second is 30.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeCdnDomainDetail&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeCdnDomainDetail|The operation that you want to perform. Set the value to **DescribeCdnDomainDetail**. |
|DomainName|String|Yes|www.yourdomain.com|The accelerated domain name. You can specify only one domain name. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|GetDomainDetailModel|Struct| |The detailed information about the accelerated domain name. |
|CdnType|String|web|The workload type of the accelerated domain name. Valid values:

 -   **web**: images and small files.
-   **download**: downloads of larges files.
-   **video**: on-demand video and audio streaming. |
|Cname|String|domain.w.alikunlun.net|The CNAME assigned to the accelerated domain name. You must add the CNAME record to the system of your DNS provider to map the accelerated domain name to the CNAME. |
|Description|String|Live streaming|The remarks of the accelerated domain. |
|DomainName|String|yourdomain.com|The accelerated domain name. |
|DomainStatus|String|online|The status of the accelerated domain name. |
|GmtCreated|String|2015-06-25T03:30:50Z|The time when the domain name was added to Alibaba Cloud Content Delivery network \(CDN\). |
|GmtModified|String|2017-06-25T03:30:50Z|The last time when the accelerated domain name was modified. |
|HttpsCname|String|yourdomain.com.alikunlun.com|The CNAME for which the HTTPS protocol is enabled. |
|ResourceGroupId|String|abcd1234abcd1234|The ID of the resource group. |
|Scope|String|domestic|The accelerated region. |
|ServerCertificateStatus|String|on|Indicates whether the Secure Sockets Layer \(SSL\) certificate is enabled.

 -   **on**: enabled
-   **off**: disabled |
|SourceModels|Array| |The information about the origin server. |
|SourceModel| | | |
|Content|String|test.com|The address of the origin server. |
|Enabled|String|online|The status of the origin server. |
|Port|Integer|80|The port that redirects back-to-origin requests. Ports 443 and 80 are supported. |
|Priority|String|20|The priority of the origin server if multiple origin servers are specified. |
|Type|String|domain|The type of the origin server. Valid values:

 -   **ipaddr**: an IP address.
-   **domain**: a domain name.
-   **oss**: an Object Storage Service \(OSS\) bucket. |
|Weight|String|10|The weight of the origin server if multiple origin servers are specified. |
|RequestId|String|18CF38AA-1275-451D-A12B-4EC0BF1C5E30|The ID of the request. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com/?Action=DescribeCdnDomainDetail
&DomainName=www.yourdomain.com
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeCdnDomainDetailResponse>
	  <GetDomainDetailModel>
		    <CdnType>web</CdnType>
		    <Cname>bb.test.com.w.kunlunle.com</Cname>
		    <DomainName>bb.test.com</DomainName>
		    <DomainStatus>online</DomainStatus>
		    <GmtCreated>2015-06-25T03:30:50Z</GmtCreated>
		    <GmtModified>2015-06-25T03:30:53Z</GmtModified>
		    <HttpsCname>bb-test-com.alikunlun.com</HttpsCname>
		    <SourceType>domain</SourceType>
		    <Region>huadong</Region>
		    <ResourceGroupId>abcd1234abcd1234</ResourceGroupId>
		    <SourceModels>
			      <SourceModel>
				        <Enabled>online</Enabled>
				        <Port>80</Port>
				        <Type>domain</Type>
				        <Content>test.com</Content>
				        <Priority>20</Priority>
			      </SourceModel>
		    </SourceModels>
		    <Sources>
			      <Source>test.com</Source>
		    </Sources>
	  </GetDomainDetailModel>
	  <RequestId>18CF38AA-1275-451D-A12B-4EC0BF1C5E30</RequestId>
</DescribeCdnDomainDetailResponse>
```

`JSON` format

```
{ "GetDomainDetailModel": { "CdnType": "web", "Cname": "bb.test.com.w.kunlunle.com", "DomainName": "bb.test.com", "DomainStatus": "online", "GmtCreated": "2015-06-25T03:30:50Z", "GmtModified": "2015-06-25T03:30:53Z", "HttpsCname": "bb-test-com.alikunlun.com", "SourceType": "domain", "Region":"huadong", "ResourceGroupId":"abcd1234abcd1234", "SourceModels": { "SourceModel": [ { "Enabled": "online", "Port": 80, "Type": "domain", "Content": "test.com", "Priority": "20" } ] }, "Sources": { "Source": [ "test.com" ] } }, "RequestId": "18CF38AA-1275-451D-A12B-4EC0BF1C5E30" }
```

## Errors

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

