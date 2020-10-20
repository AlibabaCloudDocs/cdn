# DescribeCdnDomainConfigs

Queries the configurations of an accelerated domain name. You can query the configuration of one or more features at a time.

The maximum number of times that each user can call this operation per second is 100.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeCdnDomainConfigs&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeCdnDomainConfigs|The operation that you want to perform. Set the value to **DescribeCdnDomainConfigs**. |
|DomainName|String|Yes|example.com|The accelerated domain name. You can specify only one domain name. |
|FunctionNames|String|No|aliauth|The names of the features to query. Separate multiple features with commas \(,\). |

The following table lists the features and their descriptions.

|Feature

|Description |
|---------|-------------|
|referer\_white\_list\_set

|Configures a referer whitelist |
|referer\_black\_list\_set

|Configures a referer blacklist |
|filetype\_based\_ttl\_set

|Sets an expiration rule for files. |
|path\_based\_ttl\_set

|Sets an expiration rule for directories. |
|cc\_defense

|Configures protection against HTTP flood attacks. |
|oss\_auth

|Specifies the bucket that requires OSS authentication. |
|ip\_black\_list\_set

|Configures an IP blacklist. |
|ip\_allow\_list\_set

|Configures an IP whitelist. |
|error\_page

|Redirects an error page to a specified page. |
|tesla

|Configures page optimization to accelerate access. |
|set\_req\_host\_header

|Modifies the origin host header. |
|set\_req\_header

|Modifies the custom header of back-to-origin requests. |
|set\_hashkey\_args

|Ignores URL parameters. |
|aliauth

|Configures Alibaba authentication. |
|set\_resp\_header

|Configures a response header. To verify the setting, you can check the response message in a browser. |
|video\_seek

|Configures video seeking. |
|range

|Configures object chunking. |
|gzip

|Optimizes pages using GNU zip \(Gzip\) compression. |
|https\_force

|Redirects visitors from HTTP URLs to HTTPS URLs. |
|http\_force

|Redirects visitors from HTTPS URLs to HTTP URLs. |
|alilive

|Configures the ApsaraVideo Live service. |
|forward\_scheme

|Configures the static origin protocol policy. |
|cdn\_waf

|Configures basic WAF protection features. |
|https\_origin\_sni

|Configures an origin SNI. |
|quic

|Configures Quick UDP Internet Connection \(QUIC\). |
|forward\_timeout

|Specifies the timeout period of back-to-origin requests. |
|ali\_video\_split

|Configures audio extraction. |
|ipv6

|Configures IPv6 settings. |
|ali\_video\_preview

|Configures the video preview feature.

| |
|default\_ttl\_code

|Specifies the time period after which cached data expires based on status codes. |
|ali\_ua

|Configures access control based on the user-agent header. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|DomainConfigs|Array of DomainConfig| |The configurations of the accelerated domain name. |
|DomainConfig| | | |
|ConfigId|String|6295|The ID of the configuration. |
|FunctionArgs|Array of FunctionArg| |The description of each feature. |
|FunctionArg| | | |
|ArgName|String|auth\_type|The key of the parameter. |
|ArgValue|String|req\_auth|The value of the parameter. |
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
&DomainName=www.xxx.org.cn
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
|400|Invalid%s.ValueNotSupported|FunctionName \[%s\] is not supported.|The error message returned because the specified value of the FunctionName parameter is invalid.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

