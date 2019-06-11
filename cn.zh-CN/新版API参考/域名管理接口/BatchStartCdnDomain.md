# BatchStartCdnDomain {#reference613 .reference}

调用BatchStartCdnDomain启用状态为停用的加速域名，将DomainStatus变更为Online。

**说明：** 域名对应账户如果由于欠费，或域名处于非法状态，无法正常调用该接口启用加速域名。

## 请求参数 {#section_wy0_x4o_lge .section}

|参数|类型|是否必需|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数。取值：BatchStartCdnDomain。|
|DomainNames|String|是|需要接入全站加速的域名，用`,`分隔。|

## 返回参数 {#section_it0_xjf_3h6 .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|该条任务请求ID。|

## 示例 {#section_008_qk8_mnh .section}

请求示例

``` {#codeblock_owr_gbd_9hn}
http://cdn.aliyuncs.com?Action=BatchStartCdnDomain&DomainNames=example.com&<公共请求参数>
```

正常返回示例

`JSON`格式

``` {#codeblock_x1x_cy0_vy3 .language-json}
{
  "RequestId": "0AEDAF20-4DDF-4165-8750-47FF9C1929C9"
}
```

