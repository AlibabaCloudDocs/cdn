# BatchStartCdnDomain {#reference613 .reference}

You can call the BatchStartCdnDomain operation to enable one or more CDN domains. The DomainStatus parameter of the enabled CDN domains is changed to Online.

**Note:** If a CDN domain is in an invalid state or your account has an overdue payment, the CDN domain cannot be enabled.

## Request parameters {#section_wy0_x4o_lge .section}

|Parameter|Type|Required|Description|
|:--------|:---|:-------|:----------|
|Action|String |Yes|The operation that you want to perform. Set this parameter to BatchStartCdnDomain.|
|DomainNames|String|Yes|The name of the CDN domain to be enabled. You can specify multiple domain names and separate them with commas \(`,`\)|

## Response parameters {#section_it0_xjf_3h6 .section}

|Parameter|Type|Description|
|:--------|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_008_qk8_mnh .section}

Sample request

``` {#codeblock_owr_gbd_9hn}
http://cdn.aliyuncs.com?Action=BatchStartCdnDomain&DomainNames=example.com&<Common request parameter>
```

Sample success response

`JSON` format

``` {#codeblock_x1x_cy0_vy3 .language-json}
{
  "RequestId": "0AEDAF20-4DDF-4165-8750-47FF9C1929C9"
}
```

