# DescribeDomainsBySource

Queries the domain names corresponding to origin servers under your Alibaba Cloud account.

**When you call this operation, note that:**

-   You can specify one or more origin servers. Separate multiple origin servers with commas \(,\).
-   Fuzzy match is not supported.
-   The maximum number of times that each user can call this operation per second is 30.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeDomainsBySource&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeDomainsBySource|The operation that you want to perform. Set the value to **DescribeDomainsBySource**. |
|Sources|String|Yes|aaa.source.com|The origin servers. Separate multiple origin servers with commas \(,\). |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|B0F074E5-A1AC-4B32-8EA2-6F450410D1E0|The ID of the request. |
|Sources|String|aaa.xxx.com,b.xxx.com|The origin servers. |
|DomainsList|Array of DomainsData| |The domain names corresponding to each origin server. The data is indicated by the DomainsData parameter. Data type: array. |
|DomainsData| | | |
|Source|String|b.xxx.com|A requested origin server. |
|Domains|List|b1.com|The domain names corresponding to each origin server. The domain name is indicated by the domainNames parameter. Data type: array. |
|DomainInfos|Array of domainInfo| |The detailed information about the domain name. The data is indicated by the domainInfo parameter. Data type: array. |
|domainInfo| | | |
|DomainName|String|xxx.com|The accelerated domain name. |
|Status|String|online|The status of the domain name. |
|CreateTime|String|2016-07-12T11:53:19+08:00|The time when the domain name was added to Alibaba Cloud Content Delivery Network \(CDN\). |
|UpdateTime|String|2017-03-31T04:49:00+08:00|The last time when the domain information was updated. |
|DomainCname|String|xxx.w.alikunlun.com|The CNAME assigned to the domain name. |

## Examples

Sample requests

```
https://cdn.aliyuncs.com/?Action=DescribeDomainsBySource
&Sources=aaa.source.com,b.source.com
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeDomainsBySourceResponse>
  <DomainsList>
        <DomainsData>
              <Source>aaa.example.com</Source>
              <Domains>
                    <domainNames>a1.com</domainNames>
              </Domains>
              <DomainInfos>
                    <domainInfo>
                          <DomainCname>xxx.kunlunar.com</DomainCname>
                          <Status>online</Status>
                          <CreateTime>2016-07-12T11:53:19+08:00</CreateTime>
                          <UpdateTime>2017-03-31T04:49:00+08:00</UpdateTime>
                          <DomainName>a1.com</DomainName>
                    </domainInfo>
              </DomainInfos>
        </DomainsData>
        <DomainsData>
              <Source>b.example.com</Source>
              <Domains>
                    <domainNames>b1.com</domainNames>
              </Domains>
              <DomainInfos>
                    <domainInfo>
                          <DomainCname>xxx.alikunlun.com</DomainCname>
                          <Status>online</Status>
                          <CreateTime>2017-01-13T18:01:00+08:00</CreateTime>
                          <UpdateTime>2017-01-17T21:16:16+08:00</UpdateTime>
                          <DomainName>example.com</DomainName>
                    </domainInfo>
              </DomainInfos>
        </DomainsData>
  </DomainsList>
  <RequestId>B0F074E5-A1AC-4B32-8EA2-6F450410D1E0</RequestId>
  <Sources>aaa.example.com,b.example.com</Sources>
</DescribeDomainsBySourceResponse>
```

`JSON` format

```
{
    "DomainsList": {
        "DomainsData": [
            {
                "Source": "aaa.example.com",
                "Domains": {
                    "domainNames": [
                        "a1.com" ] 
                },
                "DomainInfos": {
                    "domainInfo": [
                        {
                            "DomainCname": "xxx.kunlunar.com",
                            "Status": "online",
                            "CreateTime": "2016-07-12T11:53:19+08:00",
                            "UpdateTime": "2017-03-31T04:49:00+08:00",
                            "DomainName": "a1.com" 
                        } ] 
                } 
            },
            {
                "Source": "b.example.com",
                "Domains": {
                    "domainNames": [
                        "b1.com" ] 
                },
                "DomainInfos": {
                    "domainInfo": [
                        {
                            "DomainCname": "xxx.alikunlun.com",
                            "Status": "online",
                            "CreateTime": "2017-01-13T18:01:00+08:00",
                            "UpdateTime": "2017-01-17T21:16:16+08:00",
                            "DomainName": "example.com" 
                        } ] 
                } 
            } ] 
    },
    "RequestId": "B0F074E5-A1AC-4B32-8EA2-6F450410D1E0",
    "Sources": "aaa.example.com,b.example.com" 
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|MissingParameter|The parameter Sources miss.|The error message returned because the Sources parameter is not set.|
|400|InvalidSources.Malformed|Specified Sources is malformed.|The error message returned because the specified Sources parameter is invalid. You can specify up to 20 IP addresses that are separated with commas \(,\) or one domain name. You cannot specify both IP addresses and domain names in the same request.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

