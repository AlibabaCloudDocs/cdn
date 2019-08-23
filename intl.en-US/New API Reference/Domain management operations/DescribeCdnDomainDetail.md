# DescribeCdnDomainDetail {#reference2293 .reference}

You can call the DescribeCdnDomainDetail operation to query the basic information about a CDN domain.

## Debugging {#section_c8r_h64_2ru .section}

Alibaba Cloud provides [OpenAPI Explorer](https://api.aliyun.com/#/?product=Cdn&api=DescribeCdnDomainDetail) to simplify API usage. You can use OpenAPI Explorer to search for APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#section_25m_1p7_e6o .section}

|Parameter|Type|Required|Description|
|:--------|:---|:-------|:----------|
|Action|String |Yes|The operation that you want to perform. Set this parameter to DescribeCdnDomainDetail.|
|DomainName|String|Yes|The name of the CDN domain of which the basic information is queried.|

## Response parameters {#section_jpf_k0w_n6e .section}

|Parameter|Type|Description|
|:--------|:---|:----------|
|DomainName|String|The name of the CDN domain.|
|Cname|String|The CNAME generated for the CDN domain. You must add a CNAME record with your DNS provider to map the CDN domain name to the CNAME.|
|HttpsCname|String|The CNAME for which the HTTPS protocol is enabled.|
|DomainStatus|String|The status of the CDN domain. -   online: The CDN domain is enabled.
-   offline: The CDN domain is disabled.
-   configuring: The CDN domain is being configured.
-   configure\_failed: The CDN domain failed to be configured.
-   checking: The CDN domain is under review.
-   check\_failed: The CDN domain failed the manual review.

 |
|ServerCertificateStatus|String|Indicates whether the SSL certificate is enabled. -   on: The SSL certificate is enabled.
-   off: The SSL certificate is disabled.

 |
|GmtCreated|String|The time when the CDN domain was added.|
|GmtModified|String|The time when the CDN domain was last modified.|
|ResourceGroupId|String|The ID of the resource group.|
|Description|String|The description.|
|Scope|String|The scope.|
|SourceModels|SourceModel\[\]|The origin information of the CDN domain.|

Parameters in SourceModel

|Parameter|Type|Description|
|:--------|:---|:----------|
|Content|String|The origin address.|
|Type|String|The address type of the origin. -   ipaddr: IP address
-   domain: domain name
-   oss: URL of an Alibaba Cloud OSS bucket

 |
|Port|Integer|The port number: 443 or 80.|
|Enabled|String|The status of the origin.|
|Priority|String|The priority of the origin if multiple origins are specified.|
|Weight|String|The weight of the origin if multiple origins are specified.|

## Examples {#section_w01_vy2_t2x .section}

Sample request

``` {#codeblock_pqx_3zc_fyb}
http://cdn.aliyuncs.com?Action=DescribeCdnDomainDetail&DomainName=example.com&<Common request parameters>
```

Sample success response

`JSON` format

``` {#codeblock_a51_uuz_5wv .language-json}
{
  "GetDomainDetailModel": {
    "Cname": "example.com.w.kunlunle.com",
    "DomainName": "example.com",
    "DomainStatus": "online",
    "GmtCreated": "2015-06-25T03:30:50Z",
    "GmtModified": "2015-06-25T03:30:53Z",
    "HttpsCname": "example.com.alikunlun.com",
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

