# Notify\_URL设置 {#concept_hsf_mz2_xdb .concept}

## 功能介绍 {#section_anb_rz2_xdb .section}

视频直播场景中，流状态实时信息回调，可以及时通知您推流或断流操作结果。

## 注意事项 {#section_rgd_sz2_xdb .section}

-   原理：通过 HTTP 接口向用户服务器发送GET请求，将视频流推送成功或断流成功的状态实时反馈给用户，用户服务器通过 200 响应返回接口返回结果。
-   URL无需标识，只需可正常访问，URL 的应答有要求如下：
-   如果访问超时，会重试这个 URL，目前超时时间是 5s，重试次数是 5 次，重试间隔为 1s。

## 操作步骤 {#section_bvf_tz2_xdb .section}

举例如下：

```
http://1.1.1.1/pub?action=publish&app=xc.cdnpe.com&appname=hello&id=world&ip=42.120.74.183&node=cdnvideocenter010207116011.cm3
```

|参数|取值说明|
|:-|:---|
|time|unix 时间戳|
|usrargs|用户推流的参数|
|action|publish表示推流，publish\_done表示断流|
|app|默认为自定义的推流域名，如果未绑定推流域名即为播放域名|
|appname|应用名称|
|id|流名称|
|node|cdn接受流的节点或者机器名|
|ip|推流的客户端ip|

