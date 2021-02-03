# 获取违规URL导出任务信息

调用DescribeIllegalUrlExportTask查询违规URL导出任务。

**说明：**

-   导出文件类型为csv文件。
-   单用户调用频率为1次/秒。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeIllegalUrlExportTask&type=RPC&version=2018-05-10)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeIllegalUrlExportTask|系统规定参数。取值：**DescribeIllegalUrlExportTask**。 |
|TaskId|String|是|tu\_4b37ea97\_a7fa\_4d36\_b363\_061c1f\*\*\*\*|任务ID。您可以调用[CreateIllegalUrlExportTask](~~156492~~)获取任务ID。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|DownloadUrl|String|example.com/example\_task.csv|下载地址。当任务状态为成功时，该参数才有意义。 |
|RequestId|String|64D28B53-5902-409B-94F6-FD46680144FE|请求ID。 |
|Status|String|complete|任务状态，当返回**complete**时为成功。 |

**违规状态码对照表**

|状态码

|描述 |
|-----|----|
|gmt\_created

|封禁时间。 |
|punish\_domain

|封禁的URL对应的域名。 |
|punish\_url

|封禁的具体URL。 |
|user\_id

|封禁的URL对应的账号UID。 |
|reason

|违规原因。具体如下：

 PR001：涉黄

 PR002：涉赌

 PR003：违禁商品

 PR004：违禁商品

 PR005：违禁商品

 PR006：非法活动

 PR007：涉政

 PR008：欺诈侵权

 PR009：违法信息

 PR100：暴力破解

 PR101：DDos攻击

 PR102：钓鱼行为

 PR103：恶意DNS

 PR104：垃圾邮件

 PR107：恶意爬虫

 PR108：僵尸网络

 PR109：对外攻击

 PR201：恶意程序

 PR300：域名未实名 |

    

## 示例

请求示例

```
http(s)://cdn.aliyuncs.com/?Action=DescribeIllegalUrlExportTask
&TaskId=tu_4b37ea97_a7fa_4d36_b363_061c1f****
&<公共请求参数>
```

正常返回示例

`XML`格式

```
<DescribeIllegalUrlExportTaskResponse>
  <RequestId>64D28B53-5902-409B-94F6-FD46680144FE</RequestId>
  <Status>complete</Status>
  <DownloadUrl>example.com/example_task.csv</DownloadUrl>
</DescribeIllegalUrlExportTaskResponse>
```

`JSON`格式

```
{
    "RequestId": "64D28B53-5902-409B-94F6-FD46680144FE",
    "Status": "complete",
    "DownloadUrl": "example.com/example_task.csv"
}
```

## 错误码

访问[错误中心](https://error-center.alibabacloud.com/status/product/Cdn)查看更多错误码。

