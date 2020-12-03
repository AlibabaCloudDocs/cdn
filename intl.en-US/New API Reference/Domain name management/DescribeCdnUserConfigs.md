# DescribeCdnUserConfigs

Queries the configurations of your Content Delivery Network \(CDN\) service.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeCdnUserConfigs&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeCdnUserConfigs|The operation that you want to perform. Set the value to **DescribeCdnUserConfigs**. |
|FunctionName|String|Yes|domain\_business\_control|The configuration item that you want to query. Valid values:

 -   **domain\_business\_control**: Alibaba Cloud CDN.
-   **waf**: Web Application Firewall \(WAF\). |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Configs|Array of Config| |The configurations of Alibaba Cloud CDN. |
|ArgName|String|allow\_function|The key of the parameter.

 The configurations set by enterprise or government users. |
|ArgValue|String|\{\\"scdn\_allow\\":\[\\"cc\_rule\\",\\"ddos\_dispatch\\"\]\}|The value of the parameter. Valid values:

 -   **cc\_rule**: HTTP flood protection rules.
-   **ddos\_dispatch**: integration with Anti-DDoS.
-   **edge\_safe**: application security settings on edge nodes.
-   **blocked\_regions**: blocked regions.
-   **http\_acl\_policy**: access control list \(ACL\) rules.
-   **bot\_manager**: bot traffic management.
-   **ip\_reputation**: IP reputation library. |
|FunctionName|String|domain\_business\_control|The name of the feature. |
|RequestId|String|06D29681-B7CD-4034-A8CC-28AFFA213539|The ID of the request. |

## Examples

Sample requests

```
http(s)://cdn.aliyuncs.com? Action=DescribeCdnUserConfigs
&FunctionName=domain_business_control
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeCdnUserConfigsResponse>
  <RequestId>06D29681-B7CD-4034-A8CC-28AFFA213539</RequestId>
  <Configs>
        <FunctionName>domain_business_control</FunctionName>
        <ArgValue>{"scdn_allow":["cc_rule","ddos_dispatch"]}</ArgValue>
        <ArgName>allow_function</ArgName>
  </Configs>
</DescribeCdnUserConfigsResponse>
```

`JSON` format

```
{
    "RequestId": "06D29681-B7CD-4034-A8CC-28AFFA213539",
    "Configs": [
        {
            "FunctionName": "domain_business_control",
            "ArgValue": "{\"scdn_allow\":[\"cc_rule\",\"ddos_dispatch\"]}",
            "ArgName": "allow_function"
        }
    ]
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

