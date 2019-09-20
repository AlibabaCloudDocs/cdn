# DescribeCdnHttpsDomainList {#doc_api_Cdn_DescribeCdnHttpsDomainList .reference}

You can call this operation to query all certificate information under your account.

## Debugging {#api_explorer .section}

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeCdnHttpsDomainList&type=RPC&version=2018-05-10)

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeCdnHttpsDomainList| The operation that you want to perform. Set the value to **DescribeCdnHttpsDomainList**.

 |
|Keyword|String|No|com| The keyword to be matched.

 |
|PageNumber|Integer|No|5| The number of the page to return. Valid values: **1**to**100000**.

 |
|PageSize|Integer|No|20| The maximum number of entries to return on each page. Default value: **20**.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|CertInfos|N/A|N/A| The certificate information.

 |
|CertCommonName|String|xxx.com| The returned primary domain name of the certificate.

 |
|CertExpireTime|String|2018-12-26 14:45:09| The time when the certificate expires.

 |
|CertName|String|xxx| The name of the certificate.

 |
|CertStartTime|String|2018-11-26 14:45:09| The time when the certificate starts to take effect.

 |
|CertStatus|String|mismatch| The returned certificate state. Valid responses:

 -   **ok**: The certificate is normal.
-   **mismatch**: The certificate does not match the domain.
-   **expired**: The certificate has expired.
-   **expire\_soon**: The certificate will expire soon.

 |
|CertType|String|free| The returned certificate type. Valid responses:

 -   **free**: a free certificate.
-   **cas**: a certificate purchased from Alibaba Cloud SSL Certificates Service.
-   **upload**: a user uploaded certificate.

 |
|CertUpdateTime|String|2019-01-08 18:33:16| The time when the certificate was last updated.

 |
|DomainName|String|xxx| The name of the CDN domain for which the certificate information was queried.

 |
|RequestId|String|F5E8DF64-7175-4186-9B06-F002C0BBD0C5| The ID of the request.

 |
|TotalCount|Integer|16| The total number of entries returned.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}
http(s)://cdn.aliyuncs.com? Action=DescribeCdnHttpsDomainList
&<Common request parameters>
```

Sample success responses

`XML` format

``` {#xml_return_success_demo}
<DescribeCdnHttpsDomainListResponse>
	  <CertInfos>
		    <CertInfo>
			      <CertUpdateTime>2019-01-08 18:33:16</CertUpdateTime>
			      <CertType></CertType>
			      <CertName></CertName>
			      <DomainName>xxx</DomainName>
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

``` {#json_return_success_demo}
{
	"TotalCount":16,
	"RequestId":"F5E8DF64-7175-4186-9B06-F002C0BBD0C5",
	"CertInfos":{
		"CertInfo":[
			{
				"CertUpdateTime":"2019-01-08 18:33:16",
				"CertType":"",
				"CertName":"",
				"DomainName":"xxx",
				"CertStatus":"mismatch",
				"CertExpireTime":"2018-12-26 14:45:09",
				"CertStartTime":"2018-11-26 14:45:09",
				"CertCommonName":"*.xxx.com"
			}
		]
	}
}
```

## Error codes {#section_lu8_c2b_pbf .section}

For more information about error codes, visit [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

