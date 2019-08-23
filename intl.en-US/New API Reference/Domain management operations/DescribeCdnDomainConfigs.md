# DescribeCdnDomainConfigs {#reference_90924_zh .reference}

You can call the DescribeCdnDomainConfigs operation to query one or more configurations of a CDN domain.

## Debugging {#section_cba_0ou_0t8 .section}

Alibaba Cloud provides [OpenAPI Explorer](https://api.aliyun.com/#/?product=Cdn&api=DescribeCdnDomainConfigs) to simplify API usage. You can use OpenAPI Explorer to search for APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#section_vju_2nt_rz5 .section}

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Action|String |Yes|The operation that you want to perform. Set this parameter to DescribeCdnDomainConfigs.|
|DomainName|String|Yes|The name of the CDN domain of which the configurations are queried.|
|FunctionNames|String|No|The list of features. Separate multiple feature names with commas \(`,`\).|

Features

|Feature|Description|
|-------|-----------|
|referer\_white\_list\_set|Configures the referer whitelist.|
|referer\_black\_list\_set|Configures the referer blacklist.|
|filetype\_based\_ttl\_set|Sets the expiration rules for files.|
|path\_based\_ttl\_set|Sets the expiration rules for directories.|
|cc\_defense|Configures protection against HTTP flood attacks.|
|oss\_auth|Controls the access to an OSS bucket.|
|ip\_black\_list\_set|Configures the IP blacklist.|
|ip\_white\_list\_set|Configures the IP whitelist.|
|error\_page|Redirects an error page to a specified page.|
|tesla|Configures HTML optimization for access acceleration.|
|set\_req\_header|Modifies the custom origin header.|
|set\_req\_host\_header|Modifies the origin host.|
|set\_hashkey\_args|Filters URL parameters.|
|aliauth|Configures Alibaba authentication.|
|set\_resp\_header|Sets the response header. To verify the setting, you can check the response messages on the client \(browser\).|
|video\_seek|Configures the video seeking feature.|
|range|Configures the object chunking feature.|
|gzip|Configures intelligent compression with GNU zip \(gzip\).|
|https\_force|Forces redirection of HTTP requests to HTTPS.|
|http\_force|Forces redirection of HTTPS requests to HTTP.|
|alilive|Configures the ApsaraVideo Live service.|
|forward\_scheme|Configures the origin protocol policy.|
|tmd\_signature|Sets the Taobao Missile defense \(TMD\) rules.|

## Response parameters {#section_y8r_99j_vd4 .section}

|Parameter|Type|Description|
|---------|----|-----------|
|RequestId|String|The ID of the request.|
|DomainConfigs|DomainConfig\[\]|The domain configurations returned.|

Parameters in DomainConfig

|Parameter|Type|Description|
|---------|----|-----------|
|FunctionName|String |The name of the feature.|
|Status |String|The status of the feature: success, testing, failed, or configuring.|
|ConfigId|String|The ID of the configuration.|
|FunctionArgs|FunctionArg\[\]|The parameters of each feature.|

Parameters in FunctionArg

|Parameter|Type|Description|
|---------|----|-----------|
|ArgName|String |The name of the parameter.|
|ArgValue|String |The value of the parameter.|

## Examples {#section_mjv_zfd_cfb .section}

Sample request

``` {#codeblock_ovz_9cg_uc8}
http://cdn.aliyuncs.com/?Action=DescribeCdnDomainConfigs
&DomainName=www.xxx.org.cn
&FunctionNames=aliauth
&<Common request parameters>   
```

Sample success response

`JSON` format

``` {#codeblock_0m3_q7x_t04 .language-json}
{
    "RequestId": "C80705BF-0F76-41FA-BAD1-5B59296A4E59",
    "DomainConfigs": {
        "DomainConfig": [
            {
                "Status": "success",
                "FunctionArgs": {
                    "FunctionArg": [
                        {
                            "ArgName": "auth_type",
                            "ArgValue": "req_auth"
                        },
                        {
                            "ArgName": "ali_auth_dual",
                            "ArgValue": "on"
                        }
                    ]
                },
                "ConfigId": 6295,
                "FunctionName": "aliauth"
            }
        ]
    }
}        
```

## Error codes {#section_wil_psl_xfn .section}

|Error code|Error message|HTTP status code|Description|
|----------|-------------|----------------|-----------|
|InvalidFunctionName.ValueNotSupported|FunctionName %s is not supported.|400|The error message returned because the specified feature name \(%s\) is invalid. The variable %s represents the feature name.|

