# DescribeCdnUserDomainsByFunc

Queries all accelerated domain names under your Alibaba Cloud account and their status.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeCdnUserDomainsByFunc&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeCdnUserDomainsByFunc|The operation that you want to perform. Set the value to **DescribeCdnUserDomainsByFunc**. |
|FuncId|Integer|Yes|7|The ID of the feature.

 For example, the ID of the feature that sets an expiration time for paths is 7. |
|PageNumber|Integer|No|10|The number of the page to return. Default value: **1**.

 Valid values: **1** to **100000**. |
|PageSize|Integer|No|20|The number of entries to return on each page. Default value: **20**.

 Valid values: **1** to **50**. |
|ResourceGroupId|String|No|rg-xxxxx|The ID of the resource group. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Domains|Array of PageData| |The type of the data returned. |
|PageData| | | |
|CdnType|String|web|The type of workload accelerated by Alibaba Cloud Content Delivery Network \(CDN\). Valid values:

 -   **web**: image and small file delivery.
-   **download**: large file delivery.
-   **video**: on-demand video and audio streaming.
-   **liveStream**: live streaming. |
|Cname|String|example.com.w.alikunlun.com|The canonical name \(CNAME\) assigned to the accelerated domain name. |
|Description|String|audit failed|The description of the status. |
|DomainName|String|example.com|The accelerated domain name. |
|DomainStatus|String|configure\_failed|The status of the accelerated domain name. Valid values:

 -   **online**: The domain name is enabled.
-   **offline**: The domain name is disabled.
-   **configuring**: The domain name is being configured.
-   **configure\_failed**: The domain name failed to be configured.
-   **checking**: The domain name is under review.
-   **check\_failed**: The domain name failed the review. |
|GmtCreated|String|2015-10-28T11:05:52Z|The time when the accelerated domain name was added to Alibaba Cloud CDN. |
|GmtModified|String|2015-10-29T10:15:31Z|The last time when the accelerated domain name was modified. |
|ResourceGroupId|String|rg-xxxxx|The ID of the resource group. |
|Sandbox|String|normal|Indicates whether the accelerated domain name is in a sandbox. |
|Sources|Array of Source| |The information about the origin server. |
|Source| | | |
|Content|String|1.1.1.1|The address of the origin server. |
|Port|Integer|80|The port of the origin server. |
|Priority|String|20|The priority of the origin server if multiple origin servers are specified. |
|Type|String|ipaddr|The type of the origin server. |
|Weight|String|10|The weight of the origin server if multiple origin servers are specified. |
|SslProtocol|String|on|The status of HTTPS. Valid values:

 -   **on**: enabled
-   **off**: disabled |
|PageNumber|Long|1|The number of the returned page. |
|PageSize|Long|5|The number of entries returned per page. |
|RequestId|String|AA75AADB-5E25-4970-B480-EAA1F5658483|The ID of the request. |
|TotalCount|Long|16|The total number of entries returned. |

## Examples

Sample requests

```
http(s)://cdn.aliyuncs.com? Action=DescribeCdnUserDomainsByFunc
&FuncId=7
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeCdnUserDomainsByFuncResponse>
  <PageNumber>1</PageNumber>
  <TotalCount>16</TotalCount>
  <PageSize>5</PageSize>
  <RequestId>AA75AADB-5E25-4970-B480-EAA1F5658483</RequestId>
  <Domains>
        <PageData>
              <CdnType>download</CdnType>
              <DomainStatus>configure_failed</DomainStatus>
              <DomainName>example.com</DomainName>
              <GmtModified>2015-10-28T11:05:52Z</GmtModified>
              <GmtCreated>2015-10-28T09:32:51Z</GmtCreated>
              <Description>audit failed</Description>
              <ResourceGroupId>rg-xxxxx</ResourceGroupId>
              <Sources>
                    <Source>
                          <Type>ipaddr</Type>
                          <Content>39.100.101.220</Content>
                          <Priority>20</Priority>
                          <Port>80</Port>
                          <Weight>10</Weight>
                    </Source>
              </Sources>
        </PageData>
        <PageData>
              <CdnType>web</CdnType>
              <DomainStatus>configure_failed</DomainStatus>
              <DomainName>example1.com</DomainName>
              <GmtModified>2015-10-28T11:05:50Z</GmtModified>
              <GmtCreated>2015-10-28T09:31:59Z</GmtCreated>
              <ResourceGroupId>rg-xxxxx</ResourceGroupId>
        </PageData>
        <PageData>
              <Cname>example4.com.w.alikunlun.com</Cname>
              <CdnType>video</CdnType>
              <DomainStatus>online</DomainStatus>
              <DomainName>example4.com</DomainName>
              <GmtModified>2015-10-23T09:02:11Z</GmtModified>
              <GmtCreated>2015-10-23T09:01:57Z</GmtCreated>
              <ResourceGroupId>rg-xxxxx</ResourceGroupId>
        </PageData>
  </Domains>
</DescribeCdnUserDomainsByFuncResponse>
```

`JSON` format

```
{
   "PageNumber": 1,
   "TotalCount": 16,
   "PageSize": 5,
   "RequestId": "AA75AADB-5E25-4970-B480-EAA1F5658483",
   "Domains": {
     "PageData": [
       {
         "CdnType": "download",
         "DomainStatus": "configure_failed",
         "DomainName": "example.com",
         "GmtModified": "2015-10-28T11:05:52Z",
         "GmtCreated": "2015-10-28T09:32:51Z",
         "Description": "audit failed",
         "ResourceGroupId":"rg-xxxxx",
        "Sources": {
                    "Source": [
                        {
                            "Type": "ipaddr",
                            "Content": "1.1.1.1",
                            "Priority": 20,
                            "Port": 80,
                            "Weight": 10
                        }
                    ]
              }
       },
       {
         "CdnType": "web",
         "DomainStatus": "configure_failed",
         "DomainName": "example1.com",
         "GmtModified": "2015-10-28T11:05:50Z",
         "GmtCreated": "2015-10-28T09:31:59Z",
         "ResourceGroupId":"rg-xxxxx"
       },
       {
         "Cname": "example4.com.w.alikunlun.com",
         "CdnType": "video",
         "DomainStatus": "online",
         "DomainName": "example4.com",
         "GmtModified": "2015-10-23T09:02:11Z",
         "GmtCreated": "2015-10-23T09:01:57Z",
         "ResourceGroupId":"rg-xxxxx"
       }
     ]
   }
 }
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

