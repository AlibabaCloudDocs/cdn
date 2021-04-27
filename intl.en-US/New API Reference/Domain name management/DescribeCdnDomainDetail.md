# DescribeCdnDomainDetail

Queries the basic information about an accelerated domain name.

**Note:** The maximum number of times that each user can call this operation per second is 30.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeCdnDomainDetail&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeCdnDomainDetail|The operation that you want to perform. Set the value to **DescribeCdnDomainDetail**. |
|DomainName|String|Yes|example.com|The accelerated domain name. You can specify only one domain name. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|GetDomainDetailModel|Struct| |The detailed information about the accelerated domain. |
|CdnType|String|web|The workload type of the accelerated domain name. Valid values:

 -   **web**: images and small files.
-   **download**: large files.
-   **video**: on-demand video and audio streaming. |
|Cname|String|example.com.w.kunlunle.com|The Canonical Name \(CNAME\) that is assigned to the accelerated domain name. You must add a CNAME record in the system of your DNS service provider to map the accelerated domain name to the CNAME. |
|Description|String|Live streaming|The remarks of the accelerated domain name. |
|DomainName|String|example.com|The accelerated domain name. |
|DomainStatus|String|online|The status of the accelerated domain name. Valid values:

 -   **online**: The domain name is enabled.
-   **offline**: The domain name is disabled.
-   **configuring**: The domain is being configured.
-   **configure\_failed**: The domain name failed to be configured.
-   **checking**: The domain name is under review.
-   **check\_failed**: The domain failed the review. |
|GmtCreated|String|2015-06-25T03:30:50Z|The time when the accelerated domain name was added to Alibaba Cloud CDN. |
|GmtModified|String|2017-06-25T03:30:50Z|The last time when the accelerated domain name was modified. |
|HttpsCname|String|example.com.w.kunlunle.com|The CNAME for which HTTPS is enabled. |
|ResourceGroupId|String|abcd1234abcd1234|The ID of the resource group. |
|Scope|String|domestic|The accelerated region. |
|ServerCertificateStatus|String|on|Indicates whether the Security Socket Layer \(SSL\) certificate is enabled. Valid values:

 -   **on**: The SSL certificate is enabled.
-   **off**: The SSL certificate is disabled. |
|SourceModels|Array of SourceModel| |The information about the origin server. |
|SourceModel| | | |
|Content|String|test.com|The address of the origin server. |
|Enabled|String|online|The status of the origin server. |
|Port|Integer|80|The port over which requests are redirected to the origin server. Ports 443 and 80 are supported. |
|Priority|String|20|The priority of the origin server if multiple origin servers are specified. |
|Type|String|domain|The type of origin server. Valid values:

 -   **ipaddr**: the IP address of the origin server.
-   **domain**: the domain name of the origin server.
-   **oss**: the URL of an Object Storage Service \(OSS\) bucket. |
|Weight|String|10|The weight of the origin server if multiple origin servers are specified. |
|RequestId|String|18CF38AA-1275-451D-A12B-4EC0BF1C5E30|The ID of the request. |

## Examples

Sample requests

```
http(s)://cdn.aliyuncs.com/?Action=DescribeCdnDomainDetail
&DomainName=example.com
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeCdnDomainDetailResponse>
  <GetDomainDetailModel>
        <CdnType>web</CdnType>
        <Cname>example.com.w.kunlunle.com</Cname>
        <DomainName>example.com</DomainName>
        <DomainStatus>online</DomainStatus>
        <GmtCreated>2015-06-25T03:30:50Z</GmtCreated>
        <GmtModified>2015-06-25T03:30:53Z</GmtModified>
        <HttpsCname>example.com.w.kunlunle.com</HttpsCname>
        <SourceType>domain</SourceType>
        <ResourceGroupId>abcd1234abcd1234</ResourceGroupId>
        <SourceModels>
              <SourceModel>
                    <Enabled>online</Enabled>
                    <Port>80</Port>
                    <Type>domain</Type>
                    <Content>example.com</Content>
                    <Priority>20</Priority>
                    <Weight>10</Weight>
              </SourceModel>
        </SourceModels>
  </GetDomainDetailModel>
  <RequestId>18CF38AA-1275-451D-A12B-4EC0BF1C5E30</RequestId>
</DescribeCdnDomainDetailResponse>
```

`JSON` format

```
{
  "GetDomainDetailModel": {
    "CdnType": "web",
    "Cname": "example.com.w.kunlunle.com",
    "DomainName": "example.com",
    "DomainStatus": "online",
    "GmtCreated": "2015-06-25T03:30:50Z",
    "GmtModified": "2015-06-25T03:30:53Z",
    "HttpsCname":"example.com.w.kunlunle.com",
    "SourceType":"domain",
    "ResourceGroupId":"abcd1234abcd1234",
    "SourceModels": {
        "SourceModel": [
            {
             "Enabled": "online",
             "Port": 80,
             "Type": "domain",
             "Content": "example.com",
             "Priority": "20",
             "Weight": "10"
             }
           ]
            }
  },
  "RequestId": "18CF38AA-1275-451D-A12B-4EC0BF1C5E30"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

