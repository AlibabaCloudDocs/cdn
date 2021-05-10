# 获取CDN用户流量包信息

调用DescribeCdnUserResourcePackage查询CDN用户当前流量包。

**说明：** 单用户调用频率：30次/秒。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeCdnUserResourcePackage&type=RPC&version=2018-05-10)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeCdnUserResourcePackage|系统规定参数。取值：**DescribeCdnUserResourcePackage**。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|84839536-2B7E-457D-9D8C-82E6C7D4E1A3|请求ID。 |
|ResourcePackageInfos|Array of ResourcePackageInfo| |由ResourcePackageInfo组成的数组格式。 |
|ResourcePackageInfo| | | |
|CommodityCode|String|cdnflowbag|资源包商品code。 |
|CurrCapacity|String|10995089554629|实例当前剩余容量。

 -   流量包单位：byte。
-   请求数包单位：次。 |
|DisplayName|String|CDN流量包（中国内地版）|套餐包名称。 |
|EndTime|String|2018-07-01T08:00:00Z|失效时间。 |
|InitCapacity|String|536870912000|资源包总量。

 -   流量包单位：byte。
-   请求数包单位：次。 |
|InstanceId|String|FP-ilttxc23a|实例ID。 |
|StartTime|String|2017-12-05T19:10:58Z|生效时间。 |
|Status|String|valid|资源包状态。取值：

 -   **valid**：有效。
-   **closed**：无效。 |
|TemplateName|String|CDN流量包|模版名称。 |

## 示例

请求示例

```
http(s)://cdn.aliyuncs.com/?Action=DescribeCdnUserResourcePackage
&<公共请求参数>
```

正常返回示例

`XML`格式

```
<DescribeCdnUserResourcePackageResponse>
	  <ResourcePackageInfos>
		    <ResourcePackageInfo>
			      <Status>closed</Status>
			      <InstanceId>FP-mkqgwsyui</InstanceId>
			      <CommodityCode>cdnflowbag</CommodityCode>
			      <InitCapacity>10995116277760</InitCapacity>
			      <EndTime>2017-01-30T08:00:00Z</EndTime>
			      <StartTime>2016-01-30T03:40:06Z</StartTime>
			      <DisplayName>CDN流量包（中国内地版）</DisplayName>
			      <CurrCapacity>10995089554629</CurrCapacity>
		    </ResourcePackageInfo>
		    <ResourcePackageInfo>
			      <Status>valid</Status>
			      <InstanceId>FP-ilttxc23a</InstanceId>
			      <CommodityCode>cdnflowbag</CommodityCode>
			      <InitCapacity>536870912000</InitCapacity>
			      <EndTime>2018-07-01T08:00:00Z</EndTime>
			      <StartTime>2017-07-01T01:26:41Z</StartTime>
			      <DisplayName>CDN流量包（中国内地版）</DisplayName>
			      <CurrCapacity>0</CurrCapacity>
		    </ResourcePackageInfo>
		    <ResourcePackageInfo>
			      <Status>valid</Status>
			      <InstanceId>CDNHTTPSBAG-cn-v0h0dnlq4000m9</InstanceId>
			      <CommodityCode>cdnhttpsbag</CommodityCode>
			      <InitCapacity>10000000</InitCapacity>
			      <EndTime>2018-12-06T08:00:00Z</EndTime>
			      <StartTime>2017-12-05T19:10:58Z</StartTime>
			      <DisplayName>CDN HTTPS请求数资源包</DisplayName>
			      <CurrCapacity>9999645</CurrCapacity>
		    </ResourcePackageInfo>
	  </ResourcePackageInfos>
	  <RequestId>84839536-2B7E-457D-9D8C-82E6C7D4E1A3</RequestId>
</DescribeCdnUserResourcePackageResponse>
```

`JSON`格式

```
{
    "ResourcePackageInfos": {
        "ResourcePackageInfo": [
            {
                "Status": "closed",
                "InstanceId": "FP-mkqgwsyui",
                "CommodityCode": "cdnflowbag",
                "InitCapacity": "10995116277760",
                "EndTime": "2017-01-30T08:00:00Z",
                "StartTime": "2016-01-30T03:40:06Z",
                "DisplayName": "CDN流量包（中国内地版）",
                "CurrCapacity": "10995089554629"
            },
            {
                "Status": "valid",
                "InstanceId": "FP-ilttxc23a",
                "CommodityCode": "cdnflowbag",
                "InitCapacity": "536870912000",
                "EndTime": "2018-07-01T08:00:00Z",
                "StartTime": "2017-07-01T01:26:41Z",
                "DisplayName": "CDN流量包（中国内地版）",
                "CurrCapacity": "0"
            },
            {
                "Status": "valid",
                "InstanceId": "CDNHTTPSBAG-cn-v0h0dnlq4000m9",
                "CommodityCode": "cdnhttpsbag",
                "InitCapacity": "10000000",
                "EndTime": "2018-12-06T08:00:00Z",
                "StartTime": "2017-12-05T19:10:58Z",
                "DisplayName": "CDN HTTPS请求数资源包",
                "CurrCapacity": "9999645"
            }
        ]
    },
    "RequestId": "84839536-2B7E-457D-9D8C-82E6C7D4E1A3"
}
```

## 错误码

访问[错误中心](https://error-center.alibabacloud.com/status/product/Cdn)查看更多错误码。

