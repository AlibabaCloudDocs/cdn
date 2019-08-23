# DeleteCdnDomain {#reference932 .reference}

You can call the DeleteCdnDomain operation to remove a CDN domain.

**Note:** 

-   Remove a CDN domain with caution. After the CDN domain is removed, the domain may become inaccessible. Before you remove a CDN domain, we recommend that you restore the corresponding A record at your DNS provider to ensure the accessibility.
-   After the DeleteCdnDomain operation is successful, all information about the CDN domain will be deleted. If you only want to disable a CDN domain, call the StopCdnDomain operation.

## Debugging {#section_21i_pm4_nkl .section}

Alibaba Cloud provides [OpenAPI Explorer](https://api.aliyun.com/#/?product=Cdn&api=DeleteCdnDomain) to simplify API usage. You can use OpenAPI Explorer to search for APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#section_7e6_vdu_lnp .section}

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Action|String |Yes|The operation that you want to perform. Set this parameter to DeleteCdnDomain.|
|DomainName|String|Yes|The name of the CDN domain to be removed.|
|ResourceGroupId|String|No|The ID of the resource group.|

## Response parameters {#section_lva_8ck_ce2 .section}

|Parameter|Type|Description|
|---------|----|-----------|
|RequestID|String|The ID of the request.|

## Examples {#section_z0v_vfy_ioi .section}

Sample request

``` {#codeblock_d01_w0i_fz9}
http://cdn.aliyuncs.com?Action=DeleteCdnDomain&DomainName=example.com&<Common request parameters>
```

Sample success response

`JSON` format

``` {#codeblock_a1p_5ua_yef .language-json}
{
  "RequestId": "94E3559F-7B6A-4A5E-AFFD-44E2A208A249"
}
```

## Error codes {#section_nz4_q7m_fxx .section}

|Error code|Error message|HTTP status code|Description|
|----------|-------------|----------------|-----------|
|InvaildParameter|The specific value of parameter DomainName is malformed.|400|The error message returned because the specified DomainName parameter is invalid.|

