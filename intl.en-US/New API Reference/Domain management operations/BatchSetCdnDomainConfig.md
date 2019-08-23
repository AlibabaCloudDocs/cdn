# BatchSetCdnDomainConfig {#reference4941 .reference}

You can call the BatchSetCdnDomainConfig operation to configure one or more domains.

## Debugging {#section_qp2_4ds_2vx .section}

Alibaba Cloud provides [OpenAPI Explorer](https://api.aliyun.com/#/?product=Cdn&api=BatchSetCdnDomainConfig) to simplify API usage. You can use OpenAPI Explorer to search for APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#section_s7z_e8e_qua .section}

|Parameter|Type|Required|Description|
|:--------|:---|:-------|:----------|
|Action|String |Yes|The operation that you want to perform. Set this parameter to BatchSetCdnDomainConfig.|
|DomainNames|String|Yes|The names of the CDN domains to be configured. Separate multiple domain names with commas \(`,`\).|
|Functions|Json|Yes|The list of features.|

Functions syntax

-   ``` {#codeblock_fpn_nhh_jji}
[{"functionArgs":[{"argName":"domain_name","argValue":"api.hellodtworld.com"}],"functionName":"set_req_host_header"}]
```

-   Some features, such as filetype\_based\_ttl\_set, support more than one configuration record. To update one of the configuration records, use the configId parameter to specify the record.

    ``` {#codeblock_haa_nzp_x3v}
    [{"functionArgs":[{"argName":"file_type","argValue":"jpg"},{"argName":"ttl","argValue":"18"},{"argName":"weight","argValue":"30"}],"functionName":"filetype_based_ttl_set","configId":5068995}]
    ```


Features

All parameter values are of the string type.

|Feature name|Description|Parameters|
|:-----------|:----------|:---------|
|referer\_white\_list\_set|Configures a referer whitelist.| -   refer\_domain\_allow\_list: the referer whitelist. Separate multiple referers with commas \(`,`\).
-   allow\_empty: specifies whether an empty referer is allowed. Valid values: on and off.

 |
|referer\_black\_list\_set|Configures a referer blacklist.| -   refer\_domain\_deny\_list: the referer blacklist. Separate multiple referers with commas \(`,`\).
-   allow\_empty: specifies whether an empty referer is allowed. Valid values: on and off.

 |
|filetype\_based\_ttl\_set|Sets a file expiration rule.| -   ttl: the validity period of the cached content. Unit: seconds.
-   file\_type: the file type. You can specify multiple file types and separate them with commas \(`,`\). For example, txt,jpg.
-   weight: the weight of the specified files in the cache. Valid values: 1 to 199.

 |
|path\_based\_ttl\_set|Sets a directory expiration rule.| -   ttl: the validity period of the cached content. Unit: seconds.
-   path: the directory, which must start with a forward slash \(`/`\).
-   weight: the weight of the directory in the cache. Valid values: 1 to 199.

 |
|oss\_auth|Specifies the bucket that requires OSS authentication.|oss\_bucket\_id: the URL of your OSS bucket.|
|ip\_black\_list\_set|Configures an IP blacklist.|ip\_list: the IP blacklist. Separate multiple IP addresses with commas \(`,`\).|
|ip\_allow\_list\_set|Configures an IP whitelist.|ip\_list: the IP whitelist. Separate multiple IP addresses with commas \(`,`\).|
|ip\_white\_list\_set|Specifies the IP addresses that are not blocked by the Taobao Missile Defense \(TMD\) system.|ip\_list: the list of IP addresses. Separate multiple IP addresses with commas \(`,`\).|
|error\_page|Configures error page redirection.| -   error\_code: the error code.
-   rewrite\_page: the page to which the error page will be redirected.

 |
|set\_req\_host\_header|Modifies the custom origin header.|domain\_name: the content of the origin host header.|
|set\_hashkey\_args|Filters URL parameters.| -   hashkey\_args: the parameters to be retained. Separate multiple parameters with commas \(`,`\).
-   disable: specifies whether to ignore all parameters. A value of on indicates that all parameters are ignored. A value of off indicates that not all parameters are ignored.

 |
|ali\_remove\_args|Filters and removes URL parameters.| -   ali\_remove\_args: required. It specifies the parameters to be removed. The remaining parameters are used as the URL parameters in the hashkey. Separate multiple parameters with spaces.
-   keep\_oss\_args: specifies whether to retain all origin parameters. Valid values: on and off. A value of on indicates that all origin parameters are retained. A value of off indicates that the retained parameters are the same as those of the cached hashkey.

 |
|aliauth|Configures URL authentication.| -   auth\_type: the authentication type. Valid values: no\_auth, type\_a, type\_b, and type\_c.
-   auth\_key1: the cryptographic key 1.
-   auth\_key2: the cryptographic key 2.
-   ali\_auth\_delta: the custom buffer time for authentication.

 |
|set\_resp\_header|Sets the response header. To verify the setting, you can check the response messages on the client \(browser\).| -   key: the response header field.
-   value: the content of the response header field. Enter null if you want to delete the header field.

 |
|https\_force|Configures force redirect to HTTPS.|enable: specifies whether to enable the feature. Valid values: on and off.|
|http\_force|Configures force redirect to HTTP.|enable: specifies whether to enable the feature. Valid values: on and off.|
|https\_option|Sets the basic HTTPS parameters.|http2: specifies whether to enable HTTP/2. Valid values: on and off.|
|l2\_oss\_key|Configures private bucket access control.|private\_oss\_auth: specifies whether to authenticate the access to a private OSS bucket. Valid values: on and off.|
|forward\_scheme|Specifies the origin protocol policy.| -   enable: specifies whether to enable the feature. Valid values: on and off.
-   scheme\_origin: the origin protocol. Valid values: http, https, and follow.

 |
|green\_manager|Configures illicit content moderation.|enable: specifies whether to enable the feature. Valid values: on and off.|
|tmd\_signature|Sets TMD custom rules.| -   name: the name of the rule. It must be unique within the domain name.
-   path: the URI. You can specify duplicate URIs. However, you must verify their validity.
-   pathType: the matching rule. Valid values: 0 for prefix match and 1 for exact match.
-   interval: the interval at which the data is monitored. Unit: seconds. The interval must be greater than or equal to 10 seconds.
-   count: the number of visits from an IP address.
-   action: the operation to be performed after the specified conditions are met. Valid values: 0 for access blocking and 1 for human-computer interaction.
-   ttl: the time period during which access is denied. Unit: seconds.

 |
|dynamic|Configures Dynamic Route for CDN \(DCDN\) settings.| -   enable: required. It specifies whether to enable the feature. Valid values: on and off.
-   static\_route\_type: the filename extension for static content.
-   static\_route\_url: the URI of the static content.
-   static\_route\_path: the path of the static content.
-   dynamic\_route\_origin: the origin protocol policy. Valid values: http, https, and follow.

 |
|set\_req\_header|Customizes the HTTP header for an origin request.| -   key: the header field for the origin request.
-   value: the content of the header field for the origin request.

 |
|l2\_oss\_key|Configures the private bucket access control.|private\_oss\_auth: specifies whether authentication is required for origin requests to access private OSS buckets. Valid values: on and off.|
|range|Configures object chunking.|enable: specifies whether to enable the feature. Valid values: on, off, and force.|
|video\_seek|Configures video seeking.|enable: specifies whether to enable the feature. Valid values: on and off.|
|https\_tls\_version|Specifies the TLS protocol version.| -   tls10: enables TLS 1.0. Valid values: on and off. Default value: on.
-   tls11: enables TLS 1.1. Valid values: on and off. Default value: on.
-   tls12: enables TLS 1.2. Valid values: on and off. Default value: on.
-   tls13: enables TLS 1.3. Valid values: on and off. Default value: on.

 |
|HSTS|Configures HSTS.| -   enabled: required. It specifies whether to enable the feature. Valid values: on and off. Default value: off.
-   https\_hsts\_max\_age: required. It specifies the validity period of the HSTS policy. Unit: seconds. We recommend that you set the value to 5184000 seconds \(60 days\).
-   https\_hsts\_include\_subdomains: specifies whether the HSTS header contains the IncludeSubDomains parameter. Valid values: on and off. Enable this feature with caution. Make sure that HTTPS is enabled for all subdomains of the CDN domain. Otherwise, the subdomains will become inaccessible after they are redirected to HTTPS.

 |
|filetype\_force\_ttl\_code|Configures expiration rules for file status codes.| -   file\_type: required. It specifies the file type. You can separate multiple file types with commas \(,\). Example: txt,jpg.
-   code\_string: required. It specifies the expiration setting for each status code. Example: 302=0,301=0,4xx=2.

 |
|path\_force\_ttl\_code|Configures expiration rules for directory status codes.| -   path: required. It specifies the directory that must start with a forward slash \(/\), such as /image.
-   code\_string: required. It specifies the expiration setting for each status code. Example: 302=0,301=0,4xx=2.

 |
|gzip|Configures intelligent compression.|enable: required. It specifies whether to enable the feature. Valid values: on and off.|
|tesla|Configures HTML optimization.|enable: required. It specifies whether to enable the feature. Valid values: on and off.|
|https\_origin\_sni|Configures an origin SNI.| -   enable: required. It specifies whether to enable the feature. Valid values: on and off.
-   https\_origin\_sni: required. It specifies an origin SNI.

 |
|brotli|Configures Brotli compression.| -   enable: required. It specifies whether to enable the feature. Valid values: on and off.
-   brotli\_level: the compression level. Valid values: 1 to 11.

 |
|ali\_ua|Configures a User-Agent blacklist or whitelist| -   ua: the user agent.
-   type: the list type. Valid values: black and white.

 |
|host\_redirect|Configures the rewrite rules| -   regex: the URL to be rewritten, for example, /$.
-   replacement: the target URL, for example, /go/act/sale/tbzlsy.php.
-   flag: specifies an action. Valid values: redirect and break.

 |

## Response parameters {#section_75o_7p3_u9u .section}

|Parameter|Type|Description|
|:--------|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_a2g_imy_0hv .section}

Sample request

``` {#codeblock_mxn_o14_rb0}
http://cdn.aliyuncs.com/?Action=BatchSetCdnDomainConfig
&DomainName=example.com
&Functions=[{"functionArgs":[{"argName":"domain_name","argValue":"api.hellodtworld.com"}],"functionName":"set_req_host_header"}]
&<Common request parameters>
```

Sample success response

`JSON` format

``` {#codeblock_ydx_zvi_ut9 .language-json}
{
    "RequestId": "04F0F334-1335-436C-A1D7-6C044FE73368"
}
```

## Error codes {#section_pkn_92j_u81 .section}

|Error code|Error message|HTTP status code|Description|
|:---------|:------------|:---------------|:----------|
|InvalidFunctions.Malformed|Specified Functions is malformed.|400|The error message returned because the specified Functions parameter is invalid.|
|InvalidFunctionName.ValueNotSupported|FunctionName %s is not supported.|400|The error message returned because the specified feature \(%s\) is not supported. The variable %s represents the specified feature name.|
|InvalidArgName.ValueNotSupported|ArgName %s is not supported.|400|The error message returned because the specified parameter \(%s\) is invalid. The variable %s represents the specified parameter name.|
|InvalidArgValue.Malformed|Specified ArgValue is malformed.|400|The error message returned because the specified parameter value is invalid.|

