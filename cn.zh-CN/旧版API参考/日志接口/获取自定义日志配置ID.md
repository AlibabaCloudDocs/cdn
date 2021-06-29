# 获取自定义日志配置ID

调用DescribeUserCustomLogConfig获取用户下所有自定义日志配置信息。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeUserCustomLogConfig&type=RPC&version=2014-11-11)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeUserCustomLogConfig|操作接口名，系统规定参数，取值：**DescribeUserCustomLogConfig**。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|ConfigIds|List|\["c3bb2c78-2915-4d5a-b6a1-557789255555", "25473b84-d598-498e-b148-f23d0a255555", "1f1e6c6e-6701-4193-ae4d-54bf3e555555"\]|日志配置ID。 |
|RequestId|String|94E3559F-7B6A-4A5E-AFFD-44E2A208A249|请求ID。 |

## 示例

请求示例

```
https://cdn.aliyuncs.com/?Action=DescribeUserCustomLogConfig
&公共请求参数
```

正常返回示例

`XML` 格式

```
<DescribeUserCustomLogConfigResponse>
	  <RequestId>95D5B69F-8AEC-419B-8F3A-612B35032B0D</RequestId>
	  <ConfigIds>
		    <ConfigId>c3bb2c78-2915-4d5a-b6a1-557789255555</ConfigId>
		    <ConfigId>25473b84-d598-498e-b148-f23d0a255555</ConfigId>
		    <ConfigId>1f1e6c6e-6701-4193-ae4d-54bf3e555555</ConfigId>
	  </ConfigIds>
</DescribeUserCustomLogConfigResponse>
```

`JSON` 格式

```
{
    "RequestId": "95D5B69F-8AEC-419B-8F3A-612B35032B0D",
    "ConfigIds": {
        "ConfigId": [
            "c3bb2c78-2915-4d5a-b6a1-557789255555",
            "25473b84-d598-498e-b148-f23d0a255555",
            "1f1e6c6e-6701-4193-ae4d-54bf3e555555"
        ]
    }
}
```

## 错误码

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

