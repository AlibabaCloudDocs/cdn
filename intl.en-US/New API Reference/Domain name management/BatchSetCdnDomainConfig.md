# BatchSetCdnDomainConfig

Configures multiple accelerated domain names at a time.

The maximum number of times that each user can call this operation per second is 30.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=BatchSetCdnDomainConfig&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|BatchSetCdnDomainConfig|The operation that you want to perform. Set the value to **BatchSetCdnDomainConfig**. |
|DomainNames|String|Yes|example.com|The accelerated domain names. Separate multiple domain names with commas \(,\). |
|Functions|String|Yes|\[\{"functionArgs":\[\{"argName":"domain\_name","argValue":"api.hellodtworld.com"\}\],"functionName":"set\_req\_host\_header"\}\]|A list of features in the following format:

```
[{"functionArgs":[{"argName":"Parameter key","argValue":"Parameter value"},{"argName":"xx","argValue":"xx"}],"functionName": Feature name"}]
```

You can specify one or more parameters. Separate multiple parameters with commas \(,\). |

Some features, such as filetype\_based\_ttl\_set, support multiple configuration records. If you need to update only one of the records, you can set the configuration ID \(configId\) to specify the configuration record.

```
[{"functionArgs":[{"argName":"file_type","argValue":"jpg"},{"argName":"ttl","argValue":"18"},{"argName":"weight","argValue":"30"}],"functionName":"filetype_based_ttl_set","configId":5068995}]
```

Note: Specify parameter values in the format of a string.

|Feature name

|Parameter |
|--------------|-----------|
|referer\_white\_list\_set: configures the referer whitelist.

|refer\_domain\_allow\_list: specifies the referers to be added to the whitelist. Separate multiple referers with commas \(,\).

allow\_empty: specifies whether requests with an empty referer header are allowed to access CDN resources. Valid values: on and off. |
|referer\_black\_list\_set: configures the referer blacklist.

|refer\_domain\_deny\_list: specifies the referers to be added to the blacklist. Separate multiple referers with commas \(,\).

allow\_empty: specifies whether requests with an empty referer header are allowed to access CDN resources. Valid values: on and off. |
|filetype\_based\_ttl\_set: sets an expiration rule for specific files.

|ttl: the time period after which the cached data expires. Unit: seconds.

file\_type: required. It specifies the file type. You can specify one or more file types. Separate multiple file types with commas \(,\). Example: txt,jpg

weight: specifies the weight of a file in the cache. Valid values: 1 to 199. |
|path\_based\_ttl\_set: specifies an expiration rule for specific directories.

|ttl: the time period after which the cached data expires. Unit: seconds.

path: specifies a directory, which must start with a forward slash \(/\).

weight: specifies the weight of the directory in the cache. Valid values: 1 to 99. |
|oss\_auth: configures authentication for requests destined for an Object Storage Service \(OSS\) bucket.

|oss\_bucket\_id: the endpoint of the OSS bucket. |
|ip\_black\_list\_set: configures the IP blacklist.

|ip\_list: specifies the IP addresses to be added to the whitelist. Separate multiple IP addresses with commas \(,\). |
|ip\_allow\_list\_set: configures the IP whitelist.

|ip\_list: specifies the IP addresses to be added to the whitelist. Separate multiple IP addresses with commas \(,\). |
|error\_page: redirects an error page to a specified page.

|error\_code: specifies the error code.

rewrite\_page: specifies the page to which error pages are redirected when the specified error occurs. |
|set\_req\_host\_header: configures the custom header for back-to-origin requests.

|domain\_name: specifies the custom domain name that is used as the origin host. |
|set\_hashkey\_args: reserves specified URL parameters.

|hashkey\_args: specifies the parameters to be reserved. Separate multiple parameters with commas \(,\). You can specify up to 10 parameters.

disable: specify a value of on to ignore all parameters. Specify a value of off to reserve parameters. The hashkey\_args setting has a higher priority than this setting. Even if you have set this setting to on, the parameters specified in hashkey\_args are reserved.

keep\_oss\_args: specify a value of on to reserve all parameters in back-to-origin requests. Specify a value of off to use the hashkey\_args setting. |
|aliauth: configures Alibaba authentication.

|auth\_type: specifies the authentication type. Specify a value of no\_auth to disable authentication. Specify a value of type\_a to use authentication type A. Specify a value of type\_b to use authentication type B. Specify a value of type\_c to use authentication type C.

auth\_key1: specifies the primary key. auth\_key2: specifies the secondary key.

ali\_auth\_delta: specifies the custom buffer time for authentication. |
|set\_resp\_header: sets a response header. To verify the setting, you can check the response messages in a browser.

|key: specifies the response header. This parameter is required.

value: specifies the value of the response header. Enter null if you want to delete the header.

header\_operation\_type: specifies the action of the response header. Valid values: add, delete, modify, and rewrite. add: adds the response header. delete: deletes the response header. modify: modifies the response header. rewrite: rewrites the response header.

duplicate: specifies whether duplicate response headers are allowed. Valid values: on and off.

header\_source: searches for the source of the response header.

header\_destination: replaces the response header.

match\_all: specifies whether to match all queries. |
|https\_force: redirects visitors from HTTP URLs to HTTPS URLs.

|enable: specifies whether to enable the feature. Valid values: on and off. |
|https\_force: redirects visitors from HTTPS URLs to HTTP URLs.

|enable: specifies whether to enable the feature. Valid values: on and off. |
|https\_option: configures basic parameters of HTTPS.

|http2: specifies whether to enable HTTP/2. Valid values: on and off. |
|forward\_scheme: configures the static origin protocol policy.

|enable: specifies whether to enable the feature. Valid values: on and off.

scheme\_origin: specifies the protocol policy used to communicate with the origin server. Valid values: http, https, and follow. |
|green\_manager: configures content moderation.

|enable: specifies whether to enable the feature. Valid values: on and off. |
|set\_req\_header: customizes an HTTP header for back-to-origin requests.

|key: specifies the name of the header.

value: specifies the value of the header. |
|l2\_oss\_key: retrieves content from private OSS buckets.

|private\_oss\_auth: specifies whether to enable the feature. Valid values: on and off. |
|range: configures object chunking to retrieve content from the origin server based on HTTP range requests.

|enable: specifies whether to enable the feature. Valid values: on, off, and force. |
|video\_seek: configures video seeking.

|enable: required. It specifies whether to enable the feature. Valid values: on and off.

flv\_seek\_by\_time: specifies whether to enable Flash Video \(FLV\) seeking by time. Valid values: on and off.

mp4\_seek\_start: customizes MP4 video start parameters.

mp4\_seek\_end: customizes MP4 video end parameters.

flv\_seek\_start: customizes FLV video start parameters.

flv\_seek\_end: customizes FLV video end parameters. |
|ali\_remove\_args: ignores URL parameters.

|ali\_remove\_args: required. It specifies the parameters to be ignored. The remaining parameters are used as the URL parameters in the hashkey. Separate multiple parameters with space characters.

keep\_oss\_args: specifies whether to reserve all parameters. Valid values: on and off. Specify a value of on to reserve all parameters. Specify a value of off to reserve only parameters in the hashkey. |
|https\_tls\_version: configures the TLS protocol.

|tls10: configures TLS 1.0. Valid values: on and off. Default value: on.

tls11: configures TLS 1.1. Valid values: on and off. Default value: on.

tls12: configures TLS 1.2. Valid values: on and off. Default value: on.

tls13: configures TLS 1.3. Valid values: on and off. Default value: off. |
|HSTS: configures HSTS.

|enabled: required. It specifies whether to enable HSTS. Valid values: on and off. Default value: off.

https\_hsts\_max\_age: required. It specifies the validity period of the HSTS policy. Unit: seconds. We recommend that you set the value to 5184000, which equals 60 days.

https\_hsts\_include\_subdomains: specifies whether the HSTS header contains the includeSubDomains parameter. Valid values: on and off. Proceed with caution. Make sure that HTTPS is enabled for all subdomains of the accelerated domain name. Otherwise, the subdomains will become inaccessible after they are redirected to HTTPS. |
|filetype\_force\_ttl\_code: configures an expiration rule for file status codes.

|file\_type: required. You can specify one or more file types and separate them with commas \(,\). Example: txt,jpg.

code\_string: required. It specifies the status codes. Separate multiple status codes with commas \(,\). Example: 302=0,301=0,4xx=2. |
|path\_force\_ttl\_code: configures an expiration rule for directory status codes.

|path: required. It specifies the directory, which must start with a forward slash \(/\). Example: /image

code\_string: required. It specifies the status codes. Separate multiple status codes with commas \(,\). Example: 302=0,301=0,4xx=2. |
|gzip: configures the intelligent compression feature.

|enable: required. It specifies whether to enable the feature. Valid values: on and off. |
|tesla: configures HTML optimization.

|enable: required. It specifies whether to enable the feature. Valid values: on and off. |
|https\_origin\_sni: configures an origin SNI.

|enable: required. It specifies whether to enable the origin SNI. Valid values: on and off.

https\_origin\_sni: required. It specifies the origin SNI. |
|limit\_rate: configures traffic throttling for individual requests.

|ali\_limit\_rate: required. It specifies the maximum amount of data that can be transferred per second after traffic throttling is triggered, such as 200 KM or 1 MB. The default unit is byte/s.

ali\_limit\_rate\_after: specifies the amount of data that can be sent before traffic throttling is triggered. The default unit is byte/s.

traffic\_limit\_arg: specifies the name of the URL parameter based on which traffic throttling is triggered. Example: rate.

traffic\_limit\_unit: specifies the unit for traffic throttling. Valid values: k, m, and g. For example, when the ali\_limit\_rate\_after parameter is set to 1, the maximum data transfer rate is 1 MB/s, 1 KB/s, or 1 GB/s.

ali\_limit\_start\_hour: specifies the start time of traffic throttling. Valid values: 0 to 24. Default: 0. This value must be smaller than the value of the end time.

ali\_limit\_end\_hour: specifies the end time of traffic throttling. Valid values: 0 to 24. Default: 0. This value must be greater than the value of the start time. |
|brotli: configures Brotli compression.

|enable: required. It specifies whether to enable the feature. Valid values: on and off.

brotli\_level: specifies the compression level. Valid values: 1 to 11. |
|ali\_ua: configures user-agent-based access control.

|ua: specifies user agents.

type: specifies the type of the user agent list. Valid values: black and white. |
|set\_l2\_req\_header: customizes the header of requests sent to L2 nodes.

|key: specifies the header in back-to-origin requests.

value: specifies the content of the header. Enter null if you want to delete the header. |
|host\_redirect: configures URL rewrite.

|regex: specifies the URL to be rewritten, for example, ^/$.

replacement: specifies the target URL, for example, /go/act/sale/tbzlsy.php.

flag: specifies an action. Valid values: redirect and break. |
|forward\_timeout: configures the timeout period for back-to-origin requests.

|forward\_timeout: specifies the timeout period in seconds. In most cases, specify a value that is greater than 100. |
|ali\_video\_split: configures audio extraction.

|enable: specifies whether to enable the feature. Valid values: on and off. |
|ipv6: configures IPv6.

|switch: required. It turns on or off the feature. Valid values: on and off. If you need to disable IPv6, clear the check box. Deleting the setting does not disable IPv6.

region: the region where you want to enable IPv6. You can enter an asterisk \(\*\) to specify all regions. |
|ali\_video\_preview: configures the video preview feature.

|enable: required. It specifies whether to enable this feature. Valid values: on and off. The video preview feature supports the TS and MP3 formats. For FLV and MP4 video files, visitors can advance and rewind videos.

ali\_video\_preview\_argument: required. It specifies the length of the videos that can be previewed by visitors. The parameter value must be measured in seconds. |
|default\_ttl\_code: specifies the time to live \(TTL\) for status codes.

|default\_ttl\_code: required. It specifies the default TTL for status codes. Unit: seconds. Example: 4xx=3, 200=3600, and 5xx=1. Separate multiple status codes with commas \(,\). |
|back\_to\_origin\_argument\_rewrite: rewrites parameters in back-to-origin requests.

|Action priorities: Add \> Delete \> Reserve \> Modify. Separate multiple parameters with space characters.

delete\_argument: specifies parameters to be deleted.

save\_argument: specifies parameters to be reserved. Only the specified parameters are reserved. The Reserve, Add, and Delete rules take effect at the same time.

ignore\_all\_argument: specifies whether to delete all parameters in back-to-origin requests. Valid values: on and off. However, parameters added by the Add action are reserved.

add\_argument: specifies parameters to be added. The Add action has the highest priority.

modify\_argument: specifies parameters to be modified. The Modify action has the lowest priority. Parameters specified by the Delete action are not reserved. |
|back\_to\_origin\_url\_rewrite: rewrites origin URLs.

|source\_url: required. It specifies the URL to be rewritten.

target\_url: required. It specifies the new URL to which the source URL is rewritten.

flag: specifies an action. Valid values: null, break, and enhance\_break. Null: continues to apply subsequent rewrite rules after applying the current rule. break: stops applying subsequent rewrite rules after applying the current rule. enhance\_break: applies the current rewrite rule to both the URL and its parameters, and then stops applying subsequent rules. This action is also effective on FLV streaming. |
|edge\_function: configures EdgeScript functions.

|rule: required. It specifies the domain-specific language \(DSL\) script.

pri: required. It specifies the priority of the DSL script.

enable: required. It specifies whether to enable the script. Valid values: on and off.

name: the name of the script.

pos: specifies whether to execute the script at the start or end of the request processing pipeline.

brk: after the script is matched, the subsequent scripts at the specified position are skipped.

option: an extension used to perform response header debugging.

grammar: an extension used to specify the scripting language. Valid values: es2 and js. You can also leave this parameter empty.

jsmode: an extension used to manage the domain name whitelist in JavaScript. Valid value: redirect and bypass. |
|follow\_302: configures 302 redirects.

|enable: specifies whether to enable the feature. Valid values: on and off.

max\_tries: specifies the maximum number of 302 redirects that can be performed. You can set the value to n+1. The value of n cannot be greater than 5. The default value is 3. In this case, the maximum number of redirects is three times \(2+1=3\). |
|aws\_s3\_bucket: specifies the buckets of Amazon Web Services \(AWS\) Simple Storage Service \(S3\) that require authentication.

|enable: specifies whether to enable the feature. Valid values: on and off.

bucketname: specifies the names of the AWS S3 buckets.

accesskey: required. It specifies the access key issued by AWS.

secretkey: required. it specifies the secret key issued by AWS.

region: required. It specifies the Region where the AWS S3 bucket is deployed. |
|origin\_request\_header: configures HTTP request headers.

|header\_operation\_type: required. It specifies the action in the request header. Supported actions are add, delete, modify, and rewrite. The add action adds a header. The delete action deletes a header. The modify action modifies a header. The rewrite action rewrites a header.

header\_name: required. It specifies the key of the request header.

header\_value: specifies the value of the request header.

duplicate: specifies whether to allow duplicate request headers. Valid values: on and off.

header\_source: searches for the source of the request header.

header\_destination: replaces the request header.

match\_all: specifies whether to match all queries. Valid values: on and off. |
|origin\_response\_header: configures HTTP response headers.

|header\_operation\_type: required. It specifies the action in the response header. Supported actions are add, delete, modify, and rewrite. The add action adds a response header. The delete action deletes a response header. The modify action modifies a response header. The rewrite header rewrites a response header.

header\_name: required. It specifies the key of the response header.

header\_value: specifies the value of the response header.

duplicate: specifies whether to allow duplicate response headers. Valid values: on and off.

header\_source: searches for the source of the response header.

header\_destination: replaces the response header.

match\_all: specifies whether to match all queries. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|04F0F334-1335-436C-A1D7-6C044FE73368|The ID of the request. |

## Examples

Sample requests

```
http(s)://cdn.aliyuncs.com/? Action=BatchSetCdnDomainConfig
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
|400|InvalidHeaderKey.ValueNotSupported|The specified value of parameter HeaderKey is not supported.|The error message returned because the specified Key parameter is not supported. Valid values of the Key parameter: Content-Type, Cache-Control, Content-Disposition, Content-Language, Expires, Access-Control-Allow-Origin, Access-Control-Allow-Methods, Access-Control-Allow-Headers, Access-Control-Max-Age, Access-Control-Expose-Headers, and Access-Control-Allow-Credentials.|
|400|NoPermission.SLR|The current user does not have permission to create servicelinkedrole. Please contact the Alibaba Cloud account or administrator to authorize AliyunCDNFullAccess or custom policy:Service Name:cdn-ddos.cdn.aliyuncs.com,Role: AliyunServiceRoleForCDNAccessingDDoS,Permission: ram: CreateServiceLinkedRole|The error message returned because no permission policy is attached to the service linked role. You must contact the owner of the Alibaba Cloud account or administrator to obtain the AliyunCDNFullAccess role or create a custom permission policy. Information about custom permission policies:Service name: cdn-ddos.cdn.aliyuncs.com.Name of the service linked role: AliyunServiceRoleForCDNAccessingDDoS.The required permission: ram:CreateServiceLinkedRole.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

