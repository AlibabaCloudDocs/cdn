# DescribeCdnHttpsDomainList

Queries the information about the SSL certificates under your Alibaba Cloud account.

The maximum number of times that each user can call this operation per second is 100.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeCdnHttpsDomainList&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeCdnHttpsDomainList|The operation that you want to perform. Set the value to **DescribeCdnHttpsDomainList**. |
|PageNumber|Integer|No|5|The number of the page to return. Valid values: **1** to **100000**. |
|PageSize|Integer|No|20|The maximum number of entries to return on each page. Default value: **20**. |
|Keyword|String|No|com|The keyword used for search. |

## Response parameters

|Parameter|Type|Example|Description |
|---------|----|-------|------------|
|CertInfos|Array of CertInfo| |The information about the SSL certificate. |
|CertInfo| | | |
|CertCommonName|String|\*.xxx.com|The Common Name on the SSL certificate. |
|CertExpireTime|String|2018-12-26 14:45:09|The time when the SSL certificate expires. |
|CertName|String|xxx|The name of the SSL certificate. |
|CertStartTime|String|2018-11-26 14:45:09|The time when the SSL certificate became effective. |
|CertStatus|String|mismatch|The status of the SSL certificate. Valid values:

 -   **ok**: The SSL certificate is working as expected.
-   **mismatch**: The SSL certificate does not match the specified domain name.
-   **expired**: The SSL certificate has expired.
-   **expire\_soon**: The SSL certificate will expire soon. |
|CertType|String|free|The type of the SSL certificate. Valid values:

 -   **free**: a free SSL certificate.
-   **cas**: an SSL certificate purchased from Alibaba Cloud SSL Certificates Service.
-   **upload**: a user uploaded certificate. |
|CertUpdateTime|String|2019-01-08 18:33:16|The time when the certificate was renewed. |
|DomainName|String|example.com|The accelerated domain name. |
|RequestId|String|F5E8DF64-7175-4186-9B06-F002C0BBD0C5|The ID of the request. |
|TotalCount|Integer|16|The total number of entries returned. |

## Examples

Sample requests

```
http(s)://cdn.aliyuncs.com/? Action=DescribeCdnHttpsDomainList
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeCdnHttpsDomainListResponse>
	  <CertInfos>
		    <CertInfo>
			      <CertUpdateTime>2019-01-08 18:33:16</CertUpdateTime>
			      <CertType></CertType>
			      <CertName></CertName>
			      <DomainName>example.com</DomainName>
			      <CertStatus>mismatch</CertStatus>
			      <CertExpireTime>2018-12-26 14:45:09</CertExpireTime>
			      <CertStartTime>2018-11-26 14:45:09</CertStartTime>
			      <CertCommonName>*.xxx.com</CertCommonName>
		    </CertInfo>
	  </CertInfos>
	  <TotalCount>16</TotalCount>
	  <RequestId>F5E8DF64-7175-4186-9B06-F002C0BBD0C5</RequestId>
</DescribeCdnHttpsDomainListResponse>
```

`JSON` format

```
{
    "CertInfos": {
        "CertInfo": [
            {
                "CertUpdateTime": "2019-01-08 18:33:16",
                "CertType": "",
                "CertName": "",
                "DomainName": "example.com",
                "CertStatus": "mismatch",
                "CertExpireTime": "2018-12-26 14:45:09",
                "CertStartTime": "2018-11-26 14:45:09",
                "CertCommonName": "*.xxx.com"
            }
        ]
    },
    "TotalCount": 16,
    "RequestId": "F5E8DF64-7175-4186-9B06-F002C0BBD0C5"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

