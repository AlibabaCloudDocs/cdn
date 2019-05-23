# ModifyDomainCustomLogConfig {#reference3345 .reference}

修改域名所属日志自定义日志配置信息。

## 请求参数 {#section_ubn_32b_mgb .section}

|参数|类型|是否必需|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数，取值：ModifyDomainCustomLogConfig。|
|DomainName|String|是|需要接入CDN的域名|
|ConfigId|String|是|日志配置ID|

## 返回参数 {#section_fcn_32b_mgb .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestID|String|该条任务请求ID|

## 示例 {#section_zcn_32b_mgb .section}

请求示例

```
https://cdn.aliyuncs.com?Action=ModifyDomainCustomLogConfig&DomainName=xxx&ConfigId=xxx&<公共请求参数>
```

返回示例

```
{
  "RequestId": "15C66C7B-671A-4297-9187-2C4477247A74"
}
```

## 错误码 {#section_sqb_hfb_mgb .section}

|错误码|错误信息|HTTP 状态码|描述|
|:--|:---|:-------|:-|
|InvalidConfigId|Invalid configId, configId not found or doesn't belong to current user.|404|配置信息不属于当前用户或不存在|

