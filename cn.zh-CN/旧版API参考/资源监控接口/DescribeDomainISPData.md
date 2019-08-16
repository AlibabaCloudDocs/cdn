# DescribeDomainISPData {#doc_api_Cdn_DescribeDomainISPData .reference}

调用DescribeDomainISPData接口获取加速域名天粒度的用户运营商分布数据统计。

 **调用该接口前，请您注意：** 

-   不指定**StartTime**和**EndTime**时，默认读取过去24小时的数据，同时支持按指定的起止时间查询，两者需要同时指定。
-   只支持一个域名，或当前用户下所有域名。
-   最多可获取最近90天的数据。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeDomainISPData&type=RPC&version=2014-11-11)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomainISPData|操作接口名，系统规定参数。取值：**DescribeDomainISPData**。

 |
|DomainName|String|否|test.test.com|需要查询的加速域名，只支持一个域名，不写代表当前用户下所有域名。

 |
|EndTime|String|否|2015-12-05|结束时间需大于起始时间，北京时间。

 格式为：YYYY-MM-DD。

 |
|StartTime|String|否|2015-12-05|获取数据起始时间点，北京时间。

 格式为：YYYY-MM-DD。

 不写默认读取过去24小时数据。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DataInterval|String|86400|时间间隔。

 |
|DomainName|String|test.test.com|加速域名。

 |
|EndTime|String|2016-03-14|获取数据结束时间点。

 |
|RequestId|String|DE81639B-DAC1-4C76-AB72-F34B836837D5|请求ID。

 |
|StartTime|String|2016-03-14|获取数据起始时间点。

 |
|Value| | |各运营商访问占比数据list。

 |
|AvgObjectSize|String|7081884.7|响应平均大小。单位：byte。

 |
|AvgResponseRate|String|88.92594866772144|平均响应速度。单位：byte/毫秒。

 |
|AvgResponseTime|String|79638.0|平均响应时间。单位：毫秒。

 |
|Bps|String|1311.4601296296296|带宽。

 |
|ByteHitRate|String|100.0|字节命中率。

 |
|BytesProportion|String|0.012220518530445479|总流量占比。

 |
|ISP|String|阿里巴巴|运营商信息。

 |
|IspEname|String|alibaba|运营商英文名称。

 |
|Proportion|String|0.004509176173513099|占比使用数据。

 |
|Qps|String|2.3148148148148147E-5|每秒查询率。

 |
|ReqErrRate|String|0.0|请求错误率。

 |
|ReqHitRate|String|100.0|命中。

 |
|TotalBytes|String|7081884|总流量。

 |
|TotalQuery|String|1|总请求次数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://cdn.aliyuncs.com?Action=DescribeDomainISPData
&DomainName=example.com
&StartTime=2015-12-05T00:00:00Z
&EndTime=2015-12-07T00:00:00Z
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDomainISPDataResponse>
	  <Value>
		    <ISPProportionData>
			      <ByteHitRate>100.0</ByteHitRate>
			      <TotalQuery>1</TotalQuery>
			      <Bps>1311.4601296296296</Bps>
			      <Proportion>0.004509176173513099</Proportion>
			      <AvgResponseRate>88.92594866772144</AvgResponseRate>
			      <IspEname>alibaba</IspEname>
			      <AvgObjectSize>7081884.7</AvgObjectSize>
			      <ISP>阿里巴巴</ISP>
			      <ReqErrRate>0.0</ReqErrRate>
			      <Qps>2.3148148148148147E-5</Qps>
			      <AvgResponseTime>79638.0</AvgResponseTime>
			      <ReqHitRate>100.0</ReqHitRate>
			      <TotalBytes>7081884</TotalBytes>
			      <BytesProportion>0.012220518530445479</BytesProportion>
		    </ISPProportionData>
		    <ISPProportionData>
			      <ByteHitRate>100.0</ByteHitRate>
			      <TotalQuery>3</TotalQuery>
			      <Bps>444.455</Bps>
			      <Proportion>0.013527528520539298</Proportion>
			      <AvgResponseRate>154.3345765545624</AvgResponseRate>
			      <IspEname>overseas</IspEname>
			      <AvgObjectSize>800019.0</AvgObjectSize>
			      <ISP>海外ISP</ISP>
			      <ReqErrRate>0.0</ReqErrRate>
			      <Qps>6.944444444444444E-5</Qps>
			      <AvgResponseTime>5183.666666666667</AvgResponseTime>
			      <ReqHitRate>100.0</ReqHitRate>
			      <TotalBytes>2400057</TotalBytes>
			      <BytesProportion>0.004141544558417533</BytesProportion>
		    </ISPProportionData>
		    <ISPProportionData>
			      <ByteHitRate>100.0</ByteHitRate>
			      <TotalQuery>82</TotalQuery>
			      <Bps>45838.64816666667</Bps>
			      <Proportion>0.3697524462280741</Proportion>
			      <AvgResponseRate>1025.5028528460102</AvgResponseRate>
			      <IspEname>drpeng</IspEname>
			      <AvgObjectSize>3018642.684146342</AvgObjectSize>
			      <ISP>鹏博士</ISP>
			      <ReqErrRate>0.0</ReqErrRate>
			      <Qps>0.0018981481481481482</Qps>
			      <AvgResponseTime>2943.5731707317073</AvgResponseTime>
			      <ReqHitRate>100.0</ReqHitRate>
			      <TotalBytes>247528700</TotalBytes>
			      <BytesProportion>0.42713616424581613</BytesProportion>
		    </ISPProportionData>
		    <ISPProportionData>
			      <ByteHitRate>99.99999999999999</ByteHitRate>
			      <TotalQuery>114</TotalQuery>
			      <Bps>65933.51396296297</Bps>
			      <Proportion>0.5140460837804933</Proportion>
			      <AvgResponseRate>484.6396117340071</AvgResponseRate>
			      <IspEname>cernet</IspEname>
			      <AvgObjectSize>3123166.4508771934</AvgObjectSize>
			      <ISP>教育网</ISP>
			      <ReqErrRate>0.0</ReqErrRate>
			      <Qps>0.002638888888888889</Qps>
			      <AvgResponseTime>6444.30701754386</AvgResponseTime>
			      <ReqHitRate>100.0</ReqHitRate>
			      <TotalBytes>356040975</TotalBytes>
			      <BytesProportion>0.6143852267848392</BytesProportion>
		    </ISPProportionData>
		    <ISPProportionData>
			      <ByteHitRate>100.0</ByteHitRate>
			      <TotalQuery>207</TotalQuery>
			      <Bps>81128.73735185186</Bps>
			      <Proportion>0.9333994679172115</Proportion>
			      <AvgResponseRate>752.2096624205244</AvgResponseRate>
			      <IspEname>tietong</IspEname>
			      <AvgObjectSize>2116401.843961353</AvgObjectSize>
			      <ISP>铁通</ISP>
			      <ReqErrRate>0.0</ReqErrRate>
			      <Qps>0.004791666666666666</Qps>
			      <AvgResponseTime>2813.5797101449275</AvgResponseTime>
			      <ReqHitRate>100.0</ReqHitRate>
			      <TotalBytes>438095181</TotalBytes>
			      <BytesProportion>0.7559781771177001</BytesProportion>
		    </ISPProportionData>
		    <ISPProportionData>
			      <ByteHitRate>100.00000000000001</ByteHitRate>
			      <TotalQuery>256</TotalQuery>
			      <Bps>129137.37100000001</Bps>
			      <Proportion>1.1543491004193533</Proportion>
			      <AvgResponseRate>321.5924922592767</AvgResponseRate>
			      <IspEname>other</IspEname>
			      <AvgObjectSize>2723991.4195312504</AvgObjectSize>
			      <ISP>其他</ISP>
			      <ReqErrRate>0.0</ReqErrRate>
			      <Qps>0.005925925925925926</Qps>
			      <AvgResponseTime>8470.3203125</AvgResponseTime>
			      <ReqHitRate>100.0</ReqHitRate>
			      <TotalBytes>697341803</TotalBytes>
			      <BytesProportion>1.2033348171432345</BytesProportion>
		    </ISPProportionData>
		    <ISPProportionData>
			      <ByteHitRate>99.14745652563326</ByteHitRate>
			      <TotalQuery>2866</TotalQuery>
			      <Bps>879955.1972037038</Bps>
			      <Proportion>12.923298913288543</Proportion>
			      <AvgResponseRate>1004.5513789924338</AvgResponseRate>
			      <IspEname>mobile</IspEname>
			      <AvgObjectSize>1657975.598360084</AvgObjectSize>
			      <ISP>移动</ISP>
			      <ReqErrRate>0.0</ReqErrRate>
			      <Qps>0.06634259259259259</Qps>
			      <AvgResponseTime>1650.463712491277</AvgResponseTime>
			      <ReqHitRate>97.3831123517097</ReqHitRate>
			      <TotalBytes>4751758064</TotalBytes>
			      <BytesProportion>8.19964599032574</BytesProportion>
		    </ISPProportionData>
		    <ISPProportionData>
			      <ByteHitRate>99.99981717005271</ByteHitRate>
			      <TotalQuery>6534</TotalQuery>
			      <Bps>3194660.60262963</Bps>
			      <Proportion>29.46295711773459</Proportion>
			      <AvgResponseRate>1171.525957981939</AvgResponseRate>
			      <IspEname>unicom</IspEname>
			      <AvgObjectSize>2640215.374074074</AvgObjectSize>
			      <ISP>联通</ISP>
			      <ReqErrRate>0.0</ReqErrRate>
			      <Qps>0.15125</Qps>
			      <AvgResponseTime>2253.6550352004897</AvgResponseTime>
			      <ReqHitRate>99.96939087848179</ReqHitRate>
			      <TotalBytes>17251167254</TotalBytes>
			      <BytesProportion>29.768658772680293</BytesProportion>
		    </ISPProportionData>
		    <ISPProportionData>
			      <ByteHitRate>99.99968869093071</ByteHitRate>
			      <TotalQuery>12114</TotalQuery>
			      <Bps>6333214.260796296</Bps>
			      <Proportion>54.62416016593768</Proportion>
			      <AvgResponseRate>984.184264638081</AvgResponseRate>
			      <IspEname>telecom</IspEname>
			      <AvgObjectSize>2823126.71357933</AvgObjectSize>
			      <ISP>电信</ISP>
			      <ReqErrRate>0.0</ReqErrRate>
			      <Qps>0.28041666666666665</Qps>
			      <AvgResponseTime>2868.494056463596</AvgResponseTime>
			      <ReqHitRate>99.97523526498266</ReqHitRate>
			      <TotalBytes>34199357008</TotalBytes>
			      <BytesProportion>59.01449878861353</BytesProportion>
		    </ISPProportionData>
	  </Value>
	  <DataInterval>86400</DataInterval>
	  <RequestId>DE81639B-DAC1-4C76-AB72-F34B836837D5</RequestId>
	  <DomainName>example1.com</DomainName>
	  <EndTime>2016-03-14T00:00:00Z</EndTime>
	  <StartTime>2016-03-13T00:00:00Z</StartTime>
</DescribeDomainISPDataResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Value":{
		"ISPProportionData":[
			{
				"Bps":"1311.4601296296296",
				"Proportion":"0.004509176173513099",
				"IspEname":"alibaba",
				"ISP":"阿里巴巴",
				"ReqHitRate":"100.0",
				"TotalBytes":"7081884",
				"BytesProportion":"0.012220518530445479",
				"ByteHitRate":"100.0",
				"TotalQuery":"1",
				"AvgResponseRate":"88.92594866772144",
				"AvgObjectSize":"7081884.7",
				"ReqErrRate":"0.0",
				"Qps":"2.3148148148148147E-5",
				"AvgResponseTime":"79638.0"
			},
			{
				"Bps":"444.455",
				"Proportion":"0.013527528520539298",
				"IspEname":"overseas",
				"ISP":"海外ISP",
				"ReqHitRate":"100.0",
				"TotalBytes":"2400057",
				"BytesProportion":"0.004141544558417533",
				"ByteHitRate":"100.0",
				"TotalQuery":"3",
				"AvgResponseRate":"154.3345765545624",
				"AvgObjectSize":"800019.0",
				"ReqErrRate":"0.0",
				"Qps":"6.944444444444444E-5",
				"AvgResponseTime":"5183.666666666667"
			},
			{
				"Bps":"45838.64816666667",
				"Proportion":"0.3697524462280741",
				"IspEname":"drpeng",
				"ISP":"鹏博士",
				"ReqHitRate":"100.0",
				"TotalBytes":"247528700",
				"BytesProportion":"0.42713616424581613",
				"ByteHitRate":"100.0",
				"TotalQuery":"82",
				"AvgResponseRate":"1025.5028528460102",
				"AvgObjectSize":"3018642.684146342",
				"ReqErrRate":"0.0",
				"Qps":"0.0018981481481481482",
				"AvgResponseTime":"2943.5731707317073"
			},
			{
				"Bps":"65933.51396296297",
				"Proportion":"0.5140460837804933",
				"IspEname":"cernet",
				"ISP":"教育网",
				"ReqHitRate":"100.0",
				"TotalBytes":"356040975",
				"BytesProportion":"0.6143852267848392",
				"ByteHitRate":"99.99999999999999",
				"TotalQuery":"114",
				"AvgResponseRate":"484.6396117340071",
				"AvgObjectSize":"3123166.4508771934",
				"ReqErrRate":"0.0",
				"Qps":"0.002638888888888889",
				"AvgResponseTime":"6444.30701754386"
			},
			{
				"Bps":"81128.73735185186",
				"Proportion":"0.9333994679172115",
				"IspEname":"tietong",
				"ISP":"铁通",
				"ReqHitRate":"100.0",
				"TotalBytes":"438095181",
				"BytesProportion":"0.7559781771177001",
				"ByteHitRate":"100.0",
				"TotalQuery":"207",
				"AvgResponseRate":"752.2096624205244",
				"AvgObjectSize":"2116401.843961353",
				"ReqErrRate":"0.0",
				"Qps":"0.004791666666666666",
				"AvgResponseTime":"2813.5797101449275"
			},
			{
				"Bps":"129137.37100000001",
				"Proportion":"1.1543491004193533",
				"IspEname":"other",
				"ISP":"其他",
				"ReqHitRate":"100.0",
				"TotalBytes":"697341803",
				"BytesProportion":"1.2033348171432345",
				"ByteHitRate":"100.00000000000001",
				"TotalQuery":"256",
				"AvgResponseRate":"321.5924922592767",
				"AvgObjectSize":"2723991.4195312504",
				"ReqErrRate":"0.0",
				"Qps":"0.005925925925925926",
				"AvgResponseTime":"8470.3203125"
			},
			{
				"Bps":"879955.1972037038",
				"Proportion":"12.923298913288543",
				"IspEname":"mobile",
				"ISP":"移动",
				"ReqHitRate":"97.3831123517097",
				"TotalBytes":"4751758064",
				"BytesProportion":"8.19964599032574",
				"ByteHitRate":"99.14745652563326",
				"TotalQuery":"2866",
				"AvgResponseRate":"1004.5513789924338",
				"AvgObjectSize":"1657975.598360084",
				"ReqErrRate":"0.0",
				"Qps":"0.06634259259259259",
				"AvgResponseTime":"1650.463712491277"
			},
			{
				"Bps":"3194660.60262963",
				"Proportion":"29.46295711773459",
				"IspEname":"unicom",
				"ISP":"联通",
				"ReqHitRate":"99.96939087848179",
				"TotalBytes":"17251167254",
				"BytesProportion":"29.768658772680293",
				"ByteHitRate":"99.99981717005271",
				"TotalQuery":"6534",
				"AvgResponseRate":"1171.525957981939",
				"AvgObjectSize":"2640215.374074074",
				"ReqErrRate":"0.0",
				"Qps":"0.15125",
				"AvgResponseTime":"2253.6550352004897"
			},
			{
				"Bps":"6333214.260796296",
				"Proportion":"54.62416016593768",
				"IspEname":"telecom",
				"ISP":"电信",
				"ReqHitRate":"99.97523526498266",
				"TotalBytes":"34199357008",
				"BytesProportion":"59.01449878861353",
				"ByteHitRate":"99.99968869093071",
				"TotalQuery":"12114",
				"AvgResponseRate":"984.184264638081",
				"AvgObjectSize":"2823126.71357933",
				"ReqErrRate":"0.0",
				"Qps":"0.28041666666666665",
				"AvgResponseTime":"2868.494056463596"
			}
		]
	},
	"DataInterval":"86400",
	"RequestId":"DE81639B-DAC1-4C76-AB72-F34B836837D5",
	"DomainName":"example1.com",
	"EndTime":"2016-03-14T00:00:00Z",
	"StartTime":"2016-03-13T00:00:00Z"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidStartTime.Malformed|Specified StartTime is malformed.|起始时间格式错误。日期格式请参考所调用API的帮助文档说明。|
|400|InvalidEndTime.Malformed|Specified EndTime is malformed.|结束时间格式错误。日期格式请参考所调用API的帮助文档说明。|
|400|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|开始时间设置错误，请检查更新后重试。|
|404|InvalidDomain.NotFound|The domain provided does not exist in our records.|域名不存在或不属于当前用户。请检查您填写的域名书写是否正确，或者域名是否在当前账号中，查看域名是否过期。|

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

