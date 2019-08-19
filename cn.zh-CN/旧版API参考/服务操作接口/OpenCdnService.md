# OpenCdnService {#doc_api_Cdn_OpenCdnService .reference}

调用OpenCdnService接口开通CDN服务。

 **请确保在使用该接口前，已充分了解CDN产品的收费方式和\[价格\]\(~~27271~~\)。** 

只有开通后，才能进行域名操作。

-   一个用户只能开通一次。
-   开通条件：帐号已通过实名认证。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=OpenCdnService&type=RPC&version=2014-11-11)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|OpenCdnService|操作接口名，系统规定参数。取值：**OpenCdnService**。

 |
|InternetChargeType|String|是|PayByTraffic|开通服务的计费类型。

 -   **PayByTraffic**：按流量。
-   **PayByBandwidth**：按带宽峰值。

 如果用户不指定，默认按流量。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
https://cdn.aliyuncs.com?&Action=OpenCdnService
&InternetChargeType=PayByBandwidth
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<OpenCdnServiceResponse>
    <RequestId>FD4E70AC-B791-43FA-B7BD-2DED234094C1</RequestId>
</OpenCdnServiceResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"97C68796-EB7F-4D41-9D5B-12B909D76508"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|Forbidden.Intl|User not authorized to open Intl service.|国际站CDN产品当前定向开放中，如有需求请提交\[工单处理\]\(https://workorder.console.aliyun.com/\#/ticket/scene?productId=92\)。|
|400|InvalidInternetChargeType.ValueNotSupported|The specified value of parameter "InternetChargeType" is not valid.|参数“InternetChargeType”的值无效。|
|400|CdnService.HasOpened|Your cdn service has opened.|CDN服务已开通，请勿重复开通。|
|400|InsufficientBalance|Your account does not have enough balance.|账户余额不足，请先充值再操作。|
|400|NoRealNameAuthentication|Real name authentication is needed.|您的账户未开通实名认证。|
|403|Forbidden.BidUser|Bid user is limited to open service.|您无权限使用该项服务。|
|400|FUWU\_BIZ\_COMMODITY\_VERIFY\_FAIL\_INVALID\_PAY\_METHOD|INVALID\_PAY\_METHOD|付款方式无效。|
|400|FUWU\_BIZ\_COMMODITY\_VERIFY\_FAIL\_USERPROFILECOMPLETE|MISSING\_USERPROFILE|缺少用户配置文件。|
|400|LX\_CREATE\_ORDER\_FAILED|Create order failed|订单创建失败。|

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

