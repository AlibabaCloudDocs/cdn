# DescribeCdnDomainConfigs

Queries the configurations of an accelerated domain name. You can query the configuration of one or more features at a time.

**Note:** The maximum number of times that each user can call this operation per second is 100.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different software development kits \(SDKs\).](https://api.aliyun.com/#product=Cdn&api=DescribeCdnDomainConfigs&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeCdnDomainConfigs|The operation that you want to perform. Set the value to **DescribeCdnDomainConfigs**. |
|DomainName|String|Yes|example.com|The accelerated domain name. You can specify only one domain name in each call. |
|FunctionNames|String|No|aliauth|The names of the features that you want to query. Separate multiple features with commas \(,\). |

The following table describes the features.

|Feature

|Description |
|---------|-------------|
|referer\_white\_list\_set

|Configures a referer whitelist. |
|referer\_black\_list\_set

|Configures a referer blacklist. |
|filetype\_based\_ttl\_set

|Sets expiration rules for files. |
|path\_based\_ttl\_set

|Sets expiration rules for directories. |
|oss\_auth

|Specifies the Object Storage Bucket \(OSS\) bucket that requires access authentication. |
|ip\_black\_list\_set

|Configures an IP blacklist. ip\_list: specifies the IP addresses to be added to the blacklist. Separate multiple IP addresses with commas \(,\). |
|ip\_allow\_list\_set

|Configures an IP whitelist. ip\_list: specifies the IP addresses to be added to the whitelist. Separate multiple IP addresses with commas \(,\). |
|ip\_white\_list\_set

|Configures a rate limiting list. ip\_list: specifies the IP addresses to be added to the rate limiting list. Separate multiple IP addresses with commas \(,\). |
|error\_page

|Redirects requests from an error page to a specified page. |
|tesla

|Configures the HTML optimization feature. |
|set\_req\_host\_header

|Modifies the Host header in requests before they are redirected to the origin server. |
|set\_req\_header

|Modifies custom headers in requests before they are redirected to the origin server. |
|set\_hashkey\_args

|Ignores URL parameters. |
|aliauth

|Configures Alibaba authentication. |
|set\_resp\_header

|Sets a response header. To verify this setting, you can check the response messages in a browser. |
|video\_seek

|Configures the video seeking feature. |
|range

|Configures the object chunking feature. |
|gzip

|Configures the Gzip compression feature. |
|https\_force

|Redirects requests from HTTP URLs to HTTPS URLs. |
|http\_force

|Redirects requests from HTTPS URLs to HTTP URLs. |
|alilive

|Configures the ApsaraVideo Live service. |
|forward\_scheme

|Configures the static origin protocol policy. |
|tmd\_signature

|Creates a custom rate limiting rule. |
|cdn\_waf

|Configures basic WAF protection features. |
|https\_origin\_sni

|Configures an origin Server Name Indication \(SNI\). |
|quic

|Sets basic parameters of Quick UDP Internet Connection \(QUIC\). |
|forward\_timeout

|Specifies the timeout period of requests that are redirected to the origin server. |
|ali\_video\_split

|Configures the audio extraction feature. |
|ipv6

|Configures IPv6 settings. |
|ali\_video\_preview

|Configures the video preview feature. |
|default\_ttl\_code

|Specifies a time-to-live \(TTL\) value for HTTP status codes. |
|edge\_function

|Configures EdgeScript functions. |
|follow\_302

|Configures 302 redirects. |
|aws\_s3\_bucket

|Specifies the Amazon Web Services \(AWS\) Simple Storage Service \(S3\) buckets that require authentication. |
|origin\_certificate\_verification

|Verifies certificates of requests before they are redirected to the origin server. |
|origin\_dns\_host

|Configures an origin host. |
|cc\_defense

|Sets the priorities of custom rate limiting rules. |
|cc\_rule

|Configures the rate limiting feature. |
|back\_to\_origin\_argument\_rewrite

|Rewrites parameters in requests before they are redirected to the origin server. |
|back\_to\_origin\_url\_rewrite

|Rewrites URLs in requests before they are redirected to the origin server. |
|self\_defined\_cachekey

|Configures custom cache keys. |
|advanced\_origin

|Configures advanced settings for requests that are redirected to the origin server. |
|ddos\_domain

|Configures DDoS mitigation rules. |
|ali\_location

|Blocks requests from specified regions. |
|https\_option

|Sets the basic parameters of HTTPS. Sets the basic parameters of HTTPS. Valid values:

**http2**: Specifies whether to enable HTTP/2. Valid values: on and off.

**ocsp\_stapling**: Specifies whether to enable OCSP stapling. Valid values: on and off. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|DomainConfigs|Array of DomainConfig| |The configurations of the accelerated domain name. |
|DomainConfig| | | |
|ConfigId|String|6295|The ID of the configuration. |
|FunctionArgs|Array of FunctionArg| |The description of each feature. |
|FunctionArg| | | |
|ArgName|String|auth\_type|The key of the parameter. |
|ArgValue|String|req\_auth|The value of the configuration. |
|FunctionName|String|aliauth|The name of the feature. |
|Status|String|success|The status of the configuration. Valid values:

-   **success**: The configuration has been applied.
-   **testing**: The configuration is under testing.
-   **failed**: The configuration failed.
-   **configuring**: The feature is being configured. |
|RequestId|String|C80705BF-0F76-41FA-BAD1-5B59296A4E59|The ID of the request. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com/?Action=DescribeCdnDomainConfigs
&DomainName=example.com
&FunctionNames=aliauth
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeCdnDomainConfigsResponse>
      <RequestId>C80705BF-0F76-41FA-BAD1-5B59296A4E59</RequestId>
      <DomainConfigs>
            <DomainConfig>
                  <Status>success</Status>
                  <FunctionArgs>
                        <FunctionArg>
                              <ArgName>auth_type</ArgName>
                              <ArgValue>req_auth</ArgValue>
                        </FunctionArg>
                        <FunctionArg>
                              <ArgName>ali_auth_dual</ArgName>
                              <ArgValue>on</ArgValue>
                        </FunctionArg>
                  </FunctionArgs>
                  <ConfigId>6295</ConfigId>
                  <FunctionName>aliauth</FunctionName>
            </DomainConfig>
      </DomainConfigs>
</DescribeCdnDomainConfigsResponse>
```

`JSON` format

```
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

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|Invalid%s.ValueNotSupported|FunctionName \[%s\] is not supported.|The error message returned because the FunctionName parameter is set to an invalid value.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

