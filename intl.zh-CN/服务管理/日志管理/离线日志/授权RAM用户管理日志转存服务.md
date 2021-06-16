# 授权RAM用户管理日志转存服务

RAM用户默认不支持开通及管理日志转存服务，如果您希望RAM用户可以开通或管理日志转存服务，您需要为RAM用户授权，通过创建自定义权限策略实现精细化的权限管理。

访问控制RAM（Resource Access Management）是阿里云提供的一项管理用户身份与资源访问权限的服务。通过RAM您可以创建、管理RAM用户（例如员工、系统或应用程序），并可以控制RAM用户对资源的操作权限。

## 适用场景

通过本文的授权策略，您可以为RAM用户授予日志转存服务的所有权限，包含开通、管理、查询、编辑和关闭日志转存服务。

**说明：** 由于日志转存服务的整体接口逻辑较复杂，涉及多个产品的联动授权操作，因此本文涉及的API接口未对外开放调用，建议您通过控制台进行操作。

## 步骤一：创建自定义权限策略

1.  登录[RAM控制台](https://ram.console.aliyun.com/)。

2.  在左侧导航栏，选择**权限管理** \> **权限策略管理**。

3.  单击**创建权限策略**。

4.  配置自定义权限策略信息。

    ![创建自定义策略](../images/p241583.png "创建自定义策略")

    |配置项|说明|
    |---|--|
    |**策略名称**|填入具备业务意义的名称以便后续识别。|
    |**备注**|可选填，填入该策略的备注信息。|
    |**配置模式**|选择**脚本配置**，可支持更大的配置自由度。|
    |**策略内容**|填入具体的权限策略信息，无需导入系统已有的策略。详细策略内容见表格下方。|

    为RAM用户授予日志转存服务的所有权限，包含开通、管理、查询、编辑和关闭日志转存服务。自定义权限策略如下：

    **说明：** 如果您只希望授予RAM用户部分权限，授权时仅添加需要的接口权限即可。

    ```
    {
        "Statement": [
            {
                "Action": "ram:CreateServiceLinkedRole",
                "Resource": "acs:ram:*:*:role/*",
                "Effect": "Allow",
                "Condition": {
                    "StringEquals": {
                        "ram:ServiceName": [
                            "logdelivery.cdn.aliyuncs.com"
                        ]
                    }
                }
            },
            {
                "Effect": "Allow",
                "Action": [
                    "cdn:DescribeUserDomains",
                    "cdn:CreateCdnDomainOfflineLogDelivery",
                    "cdn:DescribeCdnOfflineLogDeliveryStatus",
                    "cdn:DescribeCdnOfflineLogDelivery",
                    "cdn:DescribeCdnOfflineLogDeliveryField",
                    "cdn:DescribeCdnOfflineLogDeliveryRegions",
                    "cdn:DisableCdnDomainOfflineLogDelivery",
                    "cdn:DisableCdnOfflineLogDelivery",
                    "cdn:EnableCdnDomainOfflineLogDelivery"
                ],
                "Resource": "acs:cdn:*:*:*"
            }
        ],
        "Version": "1"
    }
    ```

    下表为您列出了自定义权限策略中涉及的各API接口的详细信息。

    |API|是否必须|用途|说明|
    |---|----|--|--|
    |DescribeUserDomains|是|查询所有域名|为RAM用户授予该接口权限后，RAM用户可以查询CDN上的所有域名，并且对阿里云账号下的所有域名拥有配置日志转存服务的权限。|
    |CreateCdnDomainOfflineLogDelivery|否|开通日志转存服务|如果您不希望RAM用户拥有开通日志转存服务的权限，请勿授权该接口。|
    |DescribeCdnOfflineLogDeliveryStatus|是|查询是否已开通日志转存服务|RAM用户查询日志转存服务的开通状态和开通日志转存服务，均需要授权该接口权限。|
    |DescribeCdnOfflineLogDelivery|是|查询日志转存服务的域名相关信息|为RAM用户授予该接口权限后，RAM用户可以查询已经开通了日志转存服务的所有域名的信息。|
    |DescribeCdnOfflineLogDeliveryField|是|查询支持的日志转存字段|RAM用户查询和开通日志转存服务过程中均需要具备该接口权限。|
    |DescribeCdnOfflineLogDeliveryRegions|是|查询日志转存服务支持的地域|无|
    |DisableCdnDomainOfflineLogDelivery|否|关闭已开通日志转存服务的域名|为RAM用户授予该接口权限后，RAM用户可以关闭已经开通了日志转存服务的全部域名，请谨慎授权。|
    |EnableCdnDomainOfflineLogDelivery|否|为新域名开通日志转存服务|为RAM用户授予该接口权限后，RAM用户可以在日志转存服务中新增域名，为新域名开通日志转存服务，请谨慎授权。|
    |DisableCdnOfflineLogDelivery|否|关闭日志转存服务|为RAM用户授予该接口权限后，RAM用户拥有关闭整个日志转存服务的权限。服务被关闭后需重新开启及配置，请谨慎授权。|

5.  单击**确定**。


## 步骤二：为RAM用户授权

1.  登录[RAM控制台](https://ram.console.aliyun.com/)。

2.  [创建RAM用户](/intl.zh-CN/用户管理/基本操作/创建RAM用户.md)。

    **说明：** 如果您已经创建了RAM用户，可跳过该步骤。

3.  在左侧导航栏，选择**人员管理** \> **用户**。

4.  找到目标RAM用户，单击**操作**列的**添加权限**。

5.  在**添加权限**面板，配置授权信息。

    ![添加自定义权限](../images/p211004.png "添加自定义权限")

    |配置项|说明|
    |---|--|
    |**授权范围**|必须选择为**云账号全部资源**，表示对应的权限应用范围为全局权限。不能选择**指定资源组**。|
    |**被授权主体**|系统根据您之前选择的目标RAM用户，已自动填充。|
    |**选择权限**|选择权限为**自定义策略**，找到您在[步骤一](#section_av0_prw_uz3)中创建的权限策略名称，并将其添加到**已选择**区域框中。|

6.  单击**确定**。

7.  单击**完成**。


[RAM用户登录控制台](/intl.zh-CN/用户管理/登录管理/RAM用户登录控制台.md)

