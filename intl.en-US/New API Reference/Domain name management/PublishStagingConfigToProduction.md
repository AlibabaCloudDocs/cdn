# PublishStagingConfigToProduction

Publishes the configurations of an accelerated domain name from the staging environment to the production environment.

The maximum number of times that each user can call this operation per second is 30.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=PublishStagingConfigToProduction&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|PublishStagingConfigToProduction|The operation that you want to perform. Set the value to **PublishStagingConfigToProduction**. |
|DomainName|String|Yes|example.com|The accelerated domain name. You can specify only one domain name. |
|FunctionName|String|Yes|aliauth|The name of the feature. |

The following table lists the descriptions of valid values of the FunctionName parameter.

|Value

|Description |
|-------|-------------|
|referer\_white\_list\_set

|Configures a referer whitelist that provides hotlinking protection. |
|referer\_black\_list\_set

|Configures a referer blacklist that provides hotlinking protection. |
|filetype\_based\_ttl\_set

|Sets a file expiration rule. |
|path\_based\_ttl\_set

|Sets a directory expiration rule. |
|oss\_auth

|Specifies the bucket that requires OSS authentication. |
|ip\_black\_list\_set

|Configures an IP blacklist. |
|ip\_white\_list\_set

|Configures an IP whitelist. |
|error\_page

|Redirects an error page to a specified page. |
|tesla

|Configures page optimization to accelerate accesse. |
|set\_req\_host\_header

|Modifies the custom header of back-to-origin requests. |
|set\_hashkey\_args

|Retains URL parameters. |
|aliauth

|Configures Alibaba Authentication. |
|set\_resp\_header

|Configures a response header. To verify the setting, you can check the response message in a browser. |
|https\_force

|Redirects visitors from HTTP URLs to HTTPS URLs. |
|http\_force

|Redirects visitors from HTTPS URLs to HTTP URLs. |
|https\_option

|Sets the basic HTTPS parameters. |
|forward\_scheme

|Configures the static origin protocol policy. |
|green\_manager

|Configures content moderation. |
|dynamic

|Configures Dynamic Route for CDN \(DCDN\) settings. |
|set\_req\_header

|Customizes the HTTP header for back-to-origin requests. |
|l2\_oss\_key

|Retrieves content from private OSS buckets. |
|range

|Configures object chunking. |
|video\_seek

|Configures video seeking. |
|set\_hashkey\_args

|Ignores the specified URL parameters. |
|https\_tls\_version

|Specifies the TLS protocol version. |
|HSTS

|HSTS |
|filetype\_force\_ttl\_code

|Configures expiration rules for file status codes. |
|path\_force\_ttl\_code

|Configures expiration rules for directory status codes. |
|gzip

|Optimizes pages using GNU zip \(Gzip\) compression. |
|tesla

|Configures page optimization to accelerate accesse. |
|https\_origin\_sni

|Configures an origin SNI. |
|limit\_rate

|Configures traffic throttling for individual requests. |
|brotli

|Configures Brotli compression. |
|ali\_ua

|Configures access control based on the user-agent header. |
|set\_l2\_req\_header

|Customizes the headers of requests sent to L2 nodes. |
|host\_redirect

|Configures URL rewrite. |
|quic

|Configures Quick UDP Internet Connection \(QUIC\). |
|forward\_timeout

|Specifies the timeout period of back-to-origin requests. |
|ali\_video\_split

|Configures audio extraction. |
|ipv6

|Configure IPv6 settings |
|back\_to\_origin\_argument\_rewrite

|Rewrites parameters in back-to-origin requests. |
|back\_to\_origin\_url\_rewrite

|Rewrites parameters in back-to-origin URLs. |
|edge\_function

|Configures EdgeScript functions. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|04F0F334-1335-436C-A1D7-6C044FE73368|The ID of the request. |

## Examples

Sample requests

```
http(s)://cdn.aliyuncs.com/? Action=PublishStagingConfigToProduction
&DomainName=example.com
&FunctionName=aliauth
&<Common request parameters>
```

Sample success responses

`XML` format

```
<PublishStagingConfigToProductionResponse>
      <RequestId>04F0F334-1335-436C-A1D7-6C044FE73368</RequestId>
</PublishStagingConfigToProductionResponse>
```

`JSON` format

```
{
  "RequestId": "04F0F334-1335-436C-A1D7-6C044FE73368"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

