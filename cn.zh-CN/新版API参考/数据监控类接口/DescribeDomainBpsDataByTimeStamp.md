# DescribeDomainBpsDataByTimeStamp {#doc_api_Cdn_DescribeDomainBpsDataByTimeStamp .reference}

调用DescribeDomainBpsDataByTimeStamp获取加速域名的在某个时刻的带宽数据。

 **调用该接口前，请您注意：** 

-   获取数据单位单位：bit/second。
-   不支持批量域名查询。
-   时间精确到5分钟粒度。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeDomainBpsDataByTimeStamp&type=RPC&version=2018-05-10)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomainBpsDataByTimeStamp|操作接口名，系统规定参数。取值：**DescribeDomainBpsDataByTimeStamp**。

 |
|DomainName|String|是|www.yourdomain.com|要查询的域名，仅支持单个查询。

 |
|IspNames|String|是|unicom,telecom|需要查询目标Isp列表，用逗号（,）隔开，不能为空， ISP名通过[DescribeCdnRegionAndIsp](~~91077~~)接口获得。

 |
|LocationNames|String|是|liaoning,guangxi|需要查询目标区域列表，用逗号（,）隔开，不能为空。Location名通过[DescribeCdnRegionAndIsp](~~91077~~)接口获得。

 |
|TimePoint|String|是|2016-08-01T22:00Z|查询目标时间点。

 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   格式为：YYYY-MM-DDThh:mm:ssZ。
-   最小数据粒度为5分钟。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DomainName|String|abc.cn|加速域名信息。

 |
|BpsDataList| | |每个区域、运营商对应的bps值。

 |
|BpsDataModel| | |每个区域、运营商对应的bps值。

 |
|LocationName|String|Liaoning|节点（区域）名。

 |
|IspName|String|unicom|运营商（Isp）名称。

 |
|Bps|Long|52119553|对应的带宽值。

 |
|TimeStamp|String|2017-12-22T08:00:00:00Z|时间片起始片刻。

 |
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID。

 |
|TimeStamp|String|2017-12-22T08:00:00:00Z|时刻。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://cdn.aliyuncs.com?Action=DescribeDomainBpsDataByTimeStamp
&DomainName=abc.com
&LocationNames=liaoning,guangxi
&IspNames=unicom,telecom
&TimePoint=2016-08-01T22:00Z
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDomainBpsDataByTimeStampResponse>
      <BpsDataList>
		    <BpsDataModel>
			      <LocationName>Liaoning</LocationName>
			      <Bps>880996111</Bps>
			      <IspName>telecom</IspName>
		    </BpsDataModel>
		    <BpsDataModel>
			      <LocationName>Liaoning</LocationName>
			      <Bps>52119553</Bps>
			      <IspName>unicom</IspName>
		    </BpsDataModel>
		    <BpsDataModel>
			      <LocationName>Guangxi</LocationName>
			      <Bps>51295137</Bps>
			      <IspName>telecom</IspName>
		    </BpsDataModel>
		    <BpsDataModel>
			      <LocationName>Guangxi</LocationName>
			      <Bps>18673571</Bps>
			      <IspName>unicom</IspName>
		    </BpsDataModel>
            <TimeStamp>2016-08-01T22:00Z</TimeStamp>
	    <RequestId>7682DE14-3B4D-48D0-9B7C-DD3C8C3E1C78</RequestId>
	    <DomainName>abc.cn</DomainName>
      </BpsDataList>
</DescribeDomainBpsDataByTimeStampResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"TimeStamp":"2016-08-01T22:00Z",
	"BpsDataList":{
		"BpsDataModel":[
			{
				"Bps":880996111,
				"IspName":"telecom",
				"LocationName":"Liaoning"
			},
			{
				"Bps":52119553,
				"IspName":"unicom",
				"LocationName":"Liaoning"
			},
			{
				"Bps":51295137,
				"IspName":"telecom",
				"LocationName":"Guangxi"
			},
			{
				"Bps":18673571,
				"IspName":"unicom",
				"LocationName":"Guangxi"
			}
		]
	},
	"RequestId":"7682DE14-3B4D-48D0-9B7C-DD3C8C3E1C78",
	"DomainName":"abc.cn"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidStartTime.Malformed|Specified StartTime is malformed.|起始时间格式错误。日期格式请参考所调用API的帮助文档说明。|
|400|InvalidEndTime.Malformed|Specified EndTime is malformed.|结束时间格式错误。日期格式请参考所调用API的帮助文档说明。|
|400|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|开始时间设置错误，请检查更新后重试。|

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

