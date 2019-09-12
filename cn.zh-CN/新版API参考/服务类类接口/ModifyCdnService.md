# ModifyCdnService {#doc_api_Cdn_ModifyCdnService .reference}

调用ModifyCdnService变更CDN服务的计费类型。

请确保在使用该接口前，已充分了解CDN产品的收费方式和[价格](https://www.aliyun.com/price/product#/cdn/detail)。

您需要先开通CDN服务才可以调用该接口。变更计费类型，次日00:00生效，多次变更以最新提交的为准。计费类型：

-   按带宽峰值计费。
-   按使用流量计费。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=ModifyCdnService&type=RPC&version=2018-05-10)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|ModifyCdnService|操作接口名，系统规定参数，取值：**ModifyCdnService**。

 |
|InternetChargeType|String|是|PayByTraffic|开通服务的计费类型：

 -   **PayByTraffic**：流量。
-   **PayByBandwidth**：带宽峰值。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
https://cdn.aliyuncs.com?&Action=ModifyCdnService
&InternetChargeType=PayByTraffic
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ModifyCdnServiceResponse>
    <RequestId>97C68796-EB7F-4D41-9D5B-12B909D76508</RequestId>
</ModifyCdnServiceResponse>
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
|400|InvalidParameter|The specified value of parameter "InternetChargeType" is not valid.|参数“InternetChargeType”的值无效。|
|400|InsufficientBalance|Your account does not have enough balance.|账户余额不足，请先充值再操作。|
|400|FUWU\_BIZ\_COMMODITY\_VERIFY\_FAIL\_INVALID\_PAY\_METHOD|INVALID\_PAY\_METHOD|付款方式无效。|
|400|FUWU\_BIZ\_COMMODITY\_VERIFY\_FAIL\_HASORDER|You have an order not yet effective|您有未生效的订单。|

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

