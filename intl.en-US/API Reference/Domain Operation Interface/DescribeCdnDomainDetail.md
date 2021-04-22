# DescribeCdnDomainDetail

Queries the basic information about an accelerated domain name.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different software development kits \(SDKs\).](https://api.aliyun.com/#product=Cdn&api=DescribeCdnDomainDetail&type=RPC&version=2014-11-11)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeCdnDomainDetail|The operation that you want to perform. Set the value to **DescribeCdnDomainDetail**. |
|DomainName|String|Yes|www.yourdomain.com|The accelerated domain name. You can specify only one domain name in each query. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|GetDomainDetailModel|Struct| |The detailed information about the accelerated domain name. |
|CdnType|String|web|The workload type of the accelerated domain name.

 -   **web**: images and small files.
-   **download**: larges files.
-   **video**: on-demand video and audio streaming.
-   **liveStream**: live streaming. |
|Cname|String|domain.w.alikunlun.net|The Canonical Name \(CNAME\) that is assigned to the accelerated domain name. You must add the CNAME record in the system of your DNS service provider to map the accelerated domain name to the CNAME. |
|Description|String|Live streaming|The remarks of the accelerated domain name. |
|DomainName|String|yourdomain.com|The accelerated domain name. |
|DomainStatus|String|online|The status of the accelerated domain name. |
|GmtCreated|String|2015-06-25T03:30:50Z|The time when the accelerated domain name was added to Alibaba Cloud Content Delivery Network \(CDN\). |
|GmtModified|String|2017-06-25T03:30:50Z|The last time when the accelerated domain name was modified. |
|HttpsCname|String|yourdomain.com.alikunlun.com|The CNAME for which the HTTPS protocol is enabled. |
|Region|String|cn-hangzhou|The region where the domain name resides. |
|ResourceGroupId|String|abcd1234abcd1234|The ID of the resource group. |
|Scope|String|domestic|The accelerated region. |
|ServerCertificateStatus|String|on|Indicates whether the Security Socket Layer \(SSL\) certificate is enabled.

 -   **on**: enabled
-   **off**: disabled |
|SourceModels|Array| |The information about the origin server. |
|SourceModel| | | |
|Content|String|test.com|The address of the origin server. |
|Enabled|String|online|The status of the origin server. |
|Port|Integer|80|The port over which requests are transmitted. Ports 443 and 80 are supported. |
|Priority|String|20|The priority of the origin server if multiple origin servers are specified. |
|Type|String|domain|The type of origin server. Valid values:

 -   **ipaddr**: a server that you can access by using an IP address.
-   **domain**: a server that you can access by using a domain name.
-   **oss**: an Object Storage Service \(OSS\) bucket. |
|SourcePort|Integer|80|The port over which requests are redirected to the origin server. |
|SourceType|String|domain|The type of the origin server. Valid values:

 -   **ipaddr**: a server that you can access by using an IP address.
-   **domain**: a server that you can access by using a domain name.
-   **oss**: an OSS bucket. |
|Sources|List|yourdomain.com|The address of the origin server. The address can be a domain name or an IP address. |
|RequestId|String|15C66C7B-671A-4297-9187-2C4477247A74|The ID of the request. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com/?Action=DescribeCdnDomainDetail
&DomainName=example.com
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeCdnDomainDetailResponse>
    <GetDomainDetailModel>
        <CdnType>web</CdnType>
        <Cname>example1.com.w.kunlunle.com</Cname>
        <DomainName>example1.com</DomainName>
        <DomainStatus>online</DomainStatus>
        <GmtCreated>2015-06-25T03:30:50Z</GmtCreated>
        <GmtModified>2015-06-25T03:30:53Z</GmtModified>
        <HttpsCname>example1.com.alikunlun.com</HttpsCname>
        <SourceType>domain</SourceType>
        <Region>huadong</Region>
        <ResourceGroupId>abcd1234abcd1234</ResourceGroupId>
        <Sources>
            <Source>example.com</Source>
        </Sources>
        <SourceModels>
              <SourceModel>
                      <Enabled>online</Enabled>
                      <Port>80</Port>
                      <Type>domain</Type>
                      <Content>example.com</Content>
                      <Priority>20</Priority>
              </SourceModel>
        </SourceModels>
    </GetDomainDetailModel>
    <RequestId>C6AAEE3B-5859-40B6-903A-884DC4C448AF</RequestId>
</DescribeCdnDomainDetailResponse>
```

`JSON` format

```
{
  "GetDomainDetailModel": {
    "CdnType": "web",
    "Cname": "example1.com.w.kunlunle.com",
    "DomainName": "example1.com",
    "DomainStatus": "online",
    "GmtCreated": "2015-06-25T03:30:50Z",
    "GmtModified": "2015-06-25T03:30:53Z",
    "HttpsCname": "example1.com.alikunlun.com",
    "SourceType": "domain",
    "Region":"huadong",
    "ResourceGroupId":"abcd1234abcd1234",
    "SourceModels": {
        "SourceModel": [
            {
             "Enabled": "online",
             "Port": 80,
             "Type": "domain",
             "Content": "example.com",
             "Priority": "20"
             }
           ]
            },
    "Sources": {
      "Source": [
        "example.com"
      ]
    }
  },
  "RequestId": "18CF38AA-1275-451D-A12B-4EC0BF1C5E30"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|InvalidParameter|Describe live region parameters have error.|The error message returned because the Region parameter is set to an invalid value.|
|400|NotExist|Not find the certificate info.|The error message returned because the specified SSL certificate does not exist.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

