# 获取公测节点有效VIP

调用DescribeStagingIp获取公测节点有效VIP。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeStagingIp&type=RPC&version=2018-05-10)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeStagingIp|操作接口名，系统规定参数，取值：**DescribeStagingIp**。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|IPV4s|List|"IPV4s":\{ "IPV4":\["xx.xx.xx.xx","xx.xx.xx.xx","xx.xx.xx.xx"\] \}|由ipv4的ip地址组成的数据格式。 |
|RequestId|String|1B9E0E83-24AC-49F4-9EE0-BF5EB03E8381|请求ID。 |

## 示例

请求示例

```
https://cdn.aliyuncs.com/?Action=DescribeStagingIp
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DescribeStagingIpResponse>
  <IPV4s>
        <IPV4>xx.xx.xx.xx</IPV4>
        <IPV4>xx.xx.xx.xx</IPV4>
        <IPV4>xx.xx.xx.xx</IPV4>
  </IPV4s>
  <RequestId>1B9E0E83-24AC-49F4-9EE0-BF5EB03E8381</RequestId>
</DescribeStagingIpResponse>
```

`JSON` 格式

```
{
     "IPV4s":{
          "IPV4":["xx.xx.xx.xx","xx.xx.xx.xx","xx.xx.xx.xx"]
              },
      "RequestId":"1B9E0E83-24AC-49F4-9EE0-BF5EB03E8381"
   }
```

## 错误码

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

