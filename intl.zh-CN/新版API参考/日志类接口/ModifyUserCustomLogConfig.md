# ModifyUserCustomLogConfig {#reference3345 .reference}

修改用户下自定义日志配置信息。

## 请求参数 {#section_ubn_32b_mgb .section}

|参数|类型|是否必需|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数，取值：ModifyUserCustomLogConfig。|
|ConfigId|String|是|日志配置ID|
|Tag|String|是|日志配置tag信息\(不超过256个字符\)|

## 返回参数 {#section_fcn_32b_mgb .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestID|String|该条任务请求ID|

## 示例 {#section_zcn_32b_mgb .section}

请求示例

```
https://cdn.aliyuncs.com?Action=ModifyUserCustomLogConfig&Tag=xxxx<公共请求参数>
```

返回示例

```
{"RequestId":"CEC1492F-EB71-4481-94CF-34BA007DC8E1"}
```

## 错误码 {#section_sqb_hfb_mgb .section}

|错误码|错误信息|HTTP 状态码|描述|
|:--|:---|:-------|:-|
|InvalidConfigId|The configId provided does not belong to you.|404|配置信息不属于当前用户或不存在|
|InvalidTag|Tag should be less than 256 characters.|403|Tag信息最多256个字符|

