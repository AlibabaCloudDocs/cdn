# CDN支持cors（跨域）配置的步骤与注意事项 {#concept_e4t_nws_xdb .concept}

目前，CDN已开放支持cors跨域访问的白名单配置功能。本文档为您介绍在使用CDN产品时如何进行cors功能配置及注意事项。

## 操作步骤 {#section_v1m_pws_xdb .section}

1.  登录[CDN控制台](https://cdn.console.aliyun.com)，单击**域名管理**。
2.  选择需要配置cors功能的域名，单击**管理**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5316/15668969923837_zh-CN.png)

3.  单击**缓存配置** \> **HTTP头**，单击**添加**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5316/15668969933838_zh-CN.png)

4.  配置参数，选择Access-Control-Allow-Origin参数。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5316/15668969933839_zh-CN.png)

    **说明：** 参数Access-Control-Allow-Origin的取值不支持多个域名。

5.  配置参数，选择Access-Control-Allow-Methods参数。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5316/15668969933840_zh-CN.png)


## 注意事项 {#section_gtr_zws_xdb .section}

-   目前不支持泛域名添加，如\*.12345.com，仅支持域名精确匹配。

-   目前仅支持配置一条白名单域名。

-   若使用OSS产品作为源站，OSS与CDN平台同时配置Cors，CDN的配置将覆盖OSS。

-   若源站为自己的服务器或ECS产品，建议先进行动静分离，静态文件使用CDN加速，CDN控制台配置的Cors功能，仅对静态文件生效。


