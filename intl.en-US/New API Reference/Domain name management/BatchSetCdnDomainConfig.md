# BatchSetCdnDomainConfig

Configures multiple accelerated domain names at a time.

**Note:** The maximum number of times that each user can call this operation per second is 30.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different software development kits \(SDKs\).](https://api.aliyun.com/#product=Cdn&api=BatchSetCdnDomainConfig&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|BatchSetCdnDomainConfig|The operation that you want to perform. Set the value to **BatchSetCdnDomainConfig**. |
|DomainNames|String|Yes|example.com|The accelerated domain names. Separate multiple accelerated domain names with commas \(,\). |
|Functions|String|Yes|\[\{"functionArgs":\[\{"argName":"domain\_name","argValue":"api.hellodtworld.com"\}\],"functionName":"set\_req\_host\_header"\}\]|The features that you want to configure. Format:

```
[{"functionArgs":[{"argName":"Parameter key","argValue":"Parameter value"},{"argName":"xx","argValue":"xx"}],"functionName": Feature name"}]
```

 Separate multiple parameters with commas \(,\). |

Some features, such as filetype\_based\_ttl\_set, support multiple configuration records. If you need to update one of the configuration records, specify the ID of the configuration record \(configId\).

```
[{"functionArgs":[{"argName":"file_type","argValue":"jpg"},{"argName":"ttl","argValue":"18"}],"functionName":"filetype_based_ttl_set","configId":5068995}]
```

Note: Specify parameter values in a string.

|Feature

|Parameter |
|---------|-----------|
|referer\_white\_list\_set: configures a referer whitelist.

|refer\_domain\_allow\_list: specifies the referers to be added to the whitelist. Separate multiple referers with commas \(,\).

 allow\_empty: specifies whether requests with an empty referer header are allowed to access CDN resources. Valid values: on and off. |
|referer\_black\_list\_set: configures a referer blacklist.

|refer\_domain\_deny\_list: specifies the referers to be added to the blacklist. Separate multiple referers with commas \(,\).

 allow\_empty: specifies whether requests with an empty referer header are allowed to access CDN resources. Valid values: on and off. |
|filetype\_based\_ttl\_set: sets an expiration rule for specified file types.

|ttl: specifies the time period after which the cached data expires. Unit: seconds.

 file\_type: specifies the file types. Separate multiple file types with commas \(,\), for example, TXT,JPG.

 weight: specifies the weight of the expiration rule. Maximum value: 99. Minimum value: 1. A greater value indicates a higher priority. |
|path\_based\_ttl\_set: sets an expiration rule for specified directories.

|ttl: specifies the time period after which the cached data expires. Unit: seconds.

 path: specifies a directory. It must start with a forward slash \(/\).

 weight: specifies the weight of the expiration rule. Maximum value: 99. Minimum value: 1. A greater value indicates a higher priority. |
|oss\_auth: configures authentication for requests destined for an Object Storage Service \(OSS\) bucket.

|oss\_bucket\_id: specifies the endpoint of the OSS bucket. |
|ip\_black\_list\_set: configures an IP blacklist.

|ip\_list: specifies the IP addresses to be added to the blacklist. Separate multiple IP addresses with commas \(,\). |
|ip\_allow\_list\_set: configures an IP whitelist.

|ip\_list: specifies the IP addresses to be added to the whitelist. Separate multiple IP addresses with commas \(,\). |
|ip\_white\_list\_set: configures an IP whitelist for rate limiting.

|ip\_list: specifies the IP addresses to be added to the whitelist. Separate multiple IP addresses with commas \(,\). |
|error\_page: redirects requests to a specified error page.

|error\_code: specifies the error code.

 rewrite\_page: specifies the error page to which requests are redirected when the specified error occurs. |
|set\_req\_host\_header: configures custom headers for requests that are redirected to the origin server.

|domain\_name: specifies a domain name that is used as the origin host. |
|set\_hashkey\_args: retains specified URL parameters.

|hashkey\_args: specifies the URL parameters to be retained. Separate multiple parameters with commas \(,\). You can specify up to 10 parameters to be retained.

 disable: A value of on indicates that all URL parameters are deleted. A value of off indicates that all URL parameters are retained. The hashkey\_args setting has a higher priority. Even if you have set this parameter to on, the parameters specified in hashkey\_args are retained.

 keep\_oss\_args: specifies whether to retain all URL parameters in requests before they are redirected to origin servers. A value of on indicates that all URL parameters are retained in requests before they are redirected to origin servers. A value of off indicates that only the parameters specified in hashkey\_args are retained. |
|aliauth: configures Alibaba Cloud authentication.

|auth\_type: specifies the authentication type. no\_auth: disables authentication. type\_a: enables signing type A. type\_b: enables signing type B. type\_c: enables signing type C.

 auth\_key1: specifies the primary authentication key. auth\_key2: specifies the secondary authentication key.

 ali\_auth\_delta: customizes the buffer time for authentication. |
|set\_resp\_header: configures an HTTP response header. To verify the setting, you can check responses in a browser.

|key: specifies the response header. This parameter is required.

 value: specifies the value of the response header. This parameter is required. Enter null if you want to delete the header.

 header\_operation\_type: specifies the action to be performed on a request header. Valid values: add, delete, modify, and rewrite. add: adds a request header. delete: deletes a request header. modify: modifies a request header. rewrite: replaces a request header.

 duplicate: specifies whether duplicate request headers are allowed. Valid values: on and off.

 header\_source: searches for the source of the request header.

 header\_destination: replaces the request header.

 match\_all: specifies whether to match all requests. Valid values: on and off. |
|https\_force: redirects visitors from HTTP URLs to corresponding HTTPS URLs.

|enable: specifies whether to enable this feature. Valid values: on and off. |
|https\_force: redirects visitors from HTTPS URLs to corresponding HTTP URLs.

|enable: specifies whether to enable this feature. Valid values: on and off. |
|https\_option: configures basic HTTPS parameters.

|http2: specifies whether to enable HTTP/2. Valid values: on and off.

 ocsp\_stapling: specifies whether to enable Online Certificate Status Protocol \(OCSP\) stapling. Valid values: on and off. |
|forward\_scheme: configures the static origin protocol policy.

|enable: specifies whether to enable this feature. Valid values: on and off.

 scheme\_origin: specifies the protocol policy that is used to communicate with the origin server. Valid values: http, https, and follow. |
|set\_req\_header: configures an HTTP header for requests that are redirected to the origin server.

|set\_req\_header is supported by version 1. We recommend that use origin\_request\_header, which is supported by version 2 and provides more features.

 key: specifies the name of the header.

 value: specifies the value of the header. |
|l2\_oss\_key: retrieves content from private OSS buckets.

|private\_oss\_auth: specifies whether to enable this feature. Valid values: on and off. |
|range: configures object chunking to retrieve content from the origin server based on HTTP range requests.

|enable: specifies whether to enable this feature. Valid values: on, off, and force. |
|video\_seek: configures video seeking.

|enable: specifies whether to enable this feature. This parameter is required. Valid values: on and off.

 flv\_seek\_by\_time: specifies whether to enable Flash Video \(FLV\) seeking by time. Valid values: on and off.

 mp4\_seek\_start: customizes MP4 video start parameters.

 mp4\_seek\_end: customizes MP4 video end parameters.

 flv\_seek\_start: customizes FLV video start parameters.

 flv\_seek\_end: customizes FLV video end parameters. |
|ali\_remove\_args: deletes URL parameters.

|ali\_remove\_args: specifies the parameters to be deleted. The remaining parameters are used as the URL parameters in hashkey\_args. Separate multiple parameters with spaces. The ali\_remove\_args parameter is required.

 keep\_oss\_args: specifies whether to retain URL parameters in requests before they are redirected to origin servers. A value of on indicates that all URL parameters are retained in requests before they are redirected to origin servers. A value of off indicates that only the parameters in the hashkey\_args are retained. |
|https\_tls\_version: configures the TLS protocol.

|tls10: configures TLS 1.0. Valid values: on and off. Default value: on.

 tls11: configures TLS 1.1. Valid values: on and off. Default value: on.

 tls12: configures TLS 1.2. Valid values: on and off. Default value: on.

 tls13: configures TLS 1.3. Valid values: on and off. Default value: off. |
|HSTS: configures HSTS.

|enabled: specifies whether to enable this feature. This parameter is required. Valid values: on and off. Default value: off.

 https\_hsts\_max\_age: specifies the validity period of the HSTS policy. This parameter is required. Unit: seconds. We recommend that you set the value to 5184000. This value equals 60 days.

 https\_hsts\_include\_subdomains: specifies whether the HSTS header contains the includeSubDomains parameter. Valid values: on and off. Use caution if you want to enable this feature. Make sure that HTTPS is enabled for all the subdomains of the domain name to be accelerated. Otherwise, the HTTPS URLs to which users are redirected from the subdomains become inaccessible. |
|filetype\_force\_ttl\_code: specifies a time-to-live \(TTL\) value for HTTP status codes based on file types.

|file\_type: specifies the file type. You can specify one or more file types. Separate multiple file types with commas \(,\), for example, TXT,JPG. This parameter is required.

 code\_string: specifies the HTTP status codes. Separate multiple status codes with commas \(,\). This parameter is required. Example: 302=0,301=0,4xx=2. |
|path\_force\_ttl\_code: specifies a TTL value for HTTP status codes based on directories.

|path: specifies a directory. It must start with a forward slash \(/\), for example, /image. This parameter is required.

 code\_string: specifies the HTTP status codes. Separate multiple status codes with commas \(,\). This parameter is required. Example: 302=0,301=0,4xx=2. |
|gzip: configures Gzip compression.

|enable: specifies whether to enable this feature. This parameter is required. Valid values: on and off. |
|tesla: configures HTML optimization.

|enable: specifies whether to enable this feature. This parameter is required. Valid values: on and off.

 trim\_js: specifies whether to optimize the JavaScript code of HTML pages. Valid values: on and off.

 trim\_css: specifies whether to optimize the CSS code of HTML pages. Valid values: on and off. |
|https\_origin\_sni: configures origin Server Name Indication \(SNI\) settings.

|enabled: specifies whether to enable this feature. This parameter is required. Valid values: on and off.

 https\_origin\_sni: specifies the origin SNI settings. This parameter is required. |
|limit\_rate: configures traffic throttling for individual requests.

|ali\_limit\_rate: specifies the maximum amount of data that can be transferred per second after traffic throttling is triggered, such as 200 KB or 1 MB. Unit: byte/s. This parameter is required.

 ali\_limit\_rate\_after: specifies the amount of data that can be sent before traffic throttling is triggered. Unit: byte/s.

 traffic\_limit\_arg: specifies the name of the URL parameter based on which traffic throttling is triggered. Example: rate.

 traffic\_limit\_unit: specifies the unit for traffic throttling. Valid values: k, m, and g. For example, when the ali\_limit\_rate\_after parameter is set to 1, the maximum data transfer rate can be 1 MB/s, 1 KB/s, or 1 GB/s.

 ali\_limit\_start\_hour: specifies the start time of traffic throttling. Valid values: 0 to 24. Default: 0. The start time must be earlier than the end time.

 ali\_limit\_end\_hour: specifies the end time of traffic throttling. Valid values: 0 to 24. Default: 24. The end time must be later than the start time. |
|brotli: configures Brotli compression.

|enable: specifies whether to enable this feature. This parameter is required. Valid values: on and off.

 brotli\_level: specifies the compression level. Valid values: 1 to 11. |
|ali\_ua: configures a user agent whitelist or blacklist.

|ua: specifies the user agents that you want to add to the list.

 type: specifies the type of the user agent list. Valid values: black and white. |
|set\_l2\_req\_header: configures HTTP headers for requests that are sent to L2 CDN nodes.

|set\_l2\_req\_header is supported by version 1. We recommend that you use origin\_request\_header, which is supported by version 2 and provides more features.

 key: specifies the name of the header.

 value: specifies the value of the header. Enter null if you want to delete the header. |
|host\_redirect: configures URL rewrite.

|regex: specifies the URL to be rewritten, for example, ^/$.

 replacement: specifies the final URL, for example, /go/act/sale/tbzlsy.php.

 flag: Valid values are redirect and break. |
|forward\_timeout: configures the timeout period for requests that are redirected to the origin server.

|forward\_timeout: specifies a time period, in seconds. We recommend that you set a value that is not greater than 100. |
|ali\_video\_split: configures audio extraction.

|enabled: specifies whether to enable this feature. Valid values: on and off. |
|ipv6: configures IPv6.

|switch: specifies whether to enable IPv6. on: enables IPv6. off: disables IPv6. This parameter is required.

 region: specifies the region where you want to enable IPv6. You can enter an asterisk \(\*\) to specify all regions. |
|ali\_video\_preview: configures video preview.

|enable: specifies whether to enable this feature. Valid values: on and off. The video preview feature supports the TS and MP3 formats. For FLV and MP4 video files, visitors can advance and rewind videos. This parameter is required.

 ali\_video\_preview\_argument: specifies the length of the videos that can be previewed by visitors. The parameter value must be measured in seconds. This parameter is required. |
|default\_ttl\_code: configures a TTL value for specified HTTP status codes.

|default\_ttl\_code: specifies a TTL value for HTTP status codes. Unit: seconds. Example: 4xx=3, 200=3600, and 5xx=1. Separate multiple status codes with commas \(,\). This parameter is required. |
|back\_to\_origin\_argument\_rewrite: configures parameter rewrite.

|Action priorities: Add \> Delete \> Reserve \> Modify. Separate multiple parameters with spaces.

 delete\_argument: specifies the parameters to be deleted.

 save\_argument: specifies the parameters to be retained. Only the specified parameters are retained. The Add and Delete rules take effect at the same time.

 ignore\_all\_argument: specifies whether to delete all parameters in requests that are redirected to the origin server. Valid values: on and off. However, parameters added by the Add action are reserved.

 add\_argument: specifies parameters to be added. The Add action has the highest priority.

 modify\_argument: specifies parameters to be modified. The Modify action has the lowest priority. Parameters specified by the Delete action are not retained. |
|back\_to\_origin\_url\_rewrite: configures URL rewrite.

|source\_url: specifies the URL to be rewritten. This parameter is required.

 target\_url: specifies the final URL. This parameter is required.

 flag: specifies an action. Valid values: null, break, and enhance\_break. null: continues to apply subsequent rewrite rules after applying the current rule. break: stops applying subsequent rewrite rules after applying the current rule. enhance\_break: applies the current rewrite rule to both the URL and its parameters, and then stops applying subsequent rules. This action is also effective on FLV streaming. |
|edge\_function: configures scripts in EdgeScript.

|rule: specifies DSL-based scripts. This parameter is required.

 pri: specifies the priority of the DSL script. This parameter is required.

 enable: specifies whether to enable the script. This parameter is required. Valid values: on and off.

 name: specifies the name of the script.

 pos: specifies whether to execute the script at the start or end of the request processing pipeline.

 brk: specifies that after the current script is matched, the subsequent scripts at the specified position are skipped.

 option: specifies extensions that are used to perform response header debugging.

 grammar: an extension used to specify the scripting language. Valid values: es2 and js. You can also leave this parameter empty.

 jsmode: an extension used to manage the domain name whitelist in JavaScript. Valid value: redirect and bypass. |
|follow\_302: configures 302 redirects.

|enable: specifies whether to enable this feature. This parameter is required. Valid values: on and off.

 max\_tries: specifies the maximum number of 302 redirects that can be performed. You can set the value to n+1. The value of n cannot be greater than 5. The default value is 3. In this case, the maximum number of redirects is three times \(2+1=3\). |
|aws\_s3\_bucket: specifies the Amazon Web Services \(AWS\) Simple Storage Service \(S3\) buckets that require authentication.

|enable: specifies whether to enable this feature. Valid values: l2 and off. This parameter is required.

 bucketname: specifies the names of the AWS S3 buckets.

 accesskey: specifies the AWS access key ID. This parameter is required.

 secretkey: specifies the AWS access key secret. This parameter is required.

 region: specifies the Region where the AWS S3 bucket is deployed. This parameter is required. |
|origin\_request\_header: configures HTTP request headers.

|header\_operation\_type: specifies the action to be performed on the request header. Valid values: add, delete, modify, and rewrite. add: adds a header. delete: deletes a header. modify: modifies a header. rewrite: rewrites a header. This parameter is required.

 header\_name: specifies the name of the request header. This parameter is required.

 header\_value: specifies the value of the request header.

 duplicate: specifies whether to allow duplicate request headers. Valid values: on and off.

 header\_source: searches for the source of the request header.

 header\_destination: replaces the request header.

 match\_all: specifies whether to match all requests. Valid values: on and off. |
|origin\_response\_header: configures HTTP response headers.

|header\_operation\_type: specifies the action to be performed on the response header. This parameter is required. Valid values: add, delete, modify, and rewrite. add: adds a response header. delete: deletes a response header. modify: modifies a response header. rewrite: rewrites a response header.

 header\_name: specifies the name of the response header. This parameter is required.

 header\_value: specifies the value of the response header.

 duplicate: specifies whether to allow duplicate response headers. Valid values: on and off.

 header\_source: searches for the source of the response header.

 header\_destination: replaces the response header.

 match\_all: specifies whether to match all responses. Valid values: on and off. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|04F0F334-1335-436C-A1D7-6C044FE73368|The ID of the request. |

## Examples

Sample requests

```
http(s)://cdn.aliyuncs.com/?Action=BatchSetCdnDomainConfig
&DomainNames=example.com
&Functions=[{"functionArgs":[{"argName":"domain_name","argValue":"api.hellodtworld.com"}],"functionName":"set_req_host_header"}]
&<Common request parameters>
```

Sample success responses

`XML` format

```
<BatchSetCdnDomainConfigResesponse>
	  <RequestId>04F0F334-1335-436C-A1D7-6C044FE73368</RequestId>
</BatchSetCdnDomainConfigResesponse>
```

`JSON` format

```
{
    "RequestId": "04F0F334-1335-436C-A1D7-6C044FE73368"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|InvalidFunctions.Malformed|The specified Functions is incorrectly formatted.|The error message returned because the format of the configuration is invalid.|
|400|InvalidHeaderKey.ValueNotSupported|The specified value of parameter HeaderKey is not supported.|The error message returned because the specified HTTP header is invalid. Valid values of the Key parameter: Content-Type, Cache-Control, Content-Disposition, Content-Language, Expires, Access-Control-Allow-Origin, Access-Control-Allow-Methods, Access-Control-Allow-Headers, Access-Control-Max-Age, Access-Control-Expose-Headers, and Access-Control-Allow-Credentials.|
|400|NoPermission.SLR|The current user does not have permission to create servicelinkedrole. Please contact the Alibaba Cloud account or administrator to authorize AliyunCDNFullAccess or custom policy:Service Name:cdn-ddos.cdn.aliyuncs.com,Role: AliyunServiceRoleForCDNAccessingDDoS,Permission: ram: CreateServiceLinkedRole|The error message returned because you do not have permissions to create service-linked roles. You must contact the owner of the Alibaba Cloud account or permission administrator to acquire the AliyunCDNFullAccess permission or attach a custom permission policy to the service-linked role. Information about the permission policy: Service name: cdn-ddos.cdn.aliyuncs.com. Name of the service-linked role: AliyunServiceRoleForCDNAccessingDDoS. Required permissions: ram:CreateServiceLinkedRole.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

