# 授予RAM用户刷新预热权限

新创建的RAM用户默认没有CDN的刷新预热权限，通过访问控制RAM（Resource Access Management）的系统授权策略或自定义授权策略，您可以授予RAM用户刷新预热权限。

您已创建RAM用户。如果未创建，请参见[创建RAM用户](/cn.zh-CN/用户管理/基本操作/创建RAM用户.md)进行创建。

默认情况下，RAM用户没有CDN的刷新预热权限，当您使用RAM用户登录CDN控制台并配置刷新预热功能时，系统会提示**该账号没有该页面接口的操作权限，或接口未支持RAM权限控制**。此时，您需要通过访问控制RAM为RAM用户授予刷新预热的权限。

![报错](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4906234261/p285875.png)

访问控制RAM支持以下两种授权策略，通过两种策略均可授予RAM用户刷新预热的权限。

-   系统策略

    由阿里云统一配置，不可修改，被授权的RAM用户将拥有管理整个CDN的权限。通过系统策略，您可以快速完成授权配置。授权方法，请参见[方法一：通过系统策略授予RAM用户刷新预热权限](#section_7l8_9g8_u83)。

-   自定义策略

    您可以自主创建、更新授权策略，进行精细化授权（例如授予RAM用户刷新预热、离线日志转存等功能操作级别的权限）。授权方法，请参见[方法二：通过自定义策略授予RAM用户刷新预热权限](#section_sx6_c72_162)。


## 方法一：通过系统策略授予RAM用户刷新预热权限

1.  登录[RAM控制台](https://ram.console.aliyun.com)。

2.  在左侧导航栏，选择**人员管理** \> **用户**。

3.  找到目标RAM用户，单击其**操作**列的**添加权限**。

    ![添加权限](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/7887283261/p283901.png)

4.  在**添加权限**面板，配置授权信息。

    ![添加系统策略](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/9152334261/p283951.png)

    1.  授权应用范围选择**整个云账号**。

    2.  选择权限为**系统策略**。

    3.  在文本框中输入AliyunCDN，系统将自动展示与CDN相关的系统权限策略。

    4.  单击**AliyunCDNFullAccess**权限策略，添加到**已选择**区域框中。

        **说明：** **AliyunCDNFullAccess**权限策略拥有CDN的完全控制权限，授权了该策略的RAM用户可以调用CDN的所有API接口和管理所有的域名。

5.  单击**确定**。

6.  单击**完成**。


## 方法二：通过自定义策略授予RAM用户刷新预热权限

1.  创建自定义权限策略。

    1.  登录[RAM控制台](https://ram.console.aliyun.com)。

    2.  在左侧导航栏，选择**权限管理** \> **权限策略管理**。

    3.  单击**创建权限策略**。

    4.  配置自定义权限策略。

        ![创建权限策略](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/0140483261/p284018.png)

        |配置项|说明|
        |---|--|
        |**策略名称**|填入具备业务意义的名称以便后续识别，本文填入AliyunCdnRefresh。|
        |**备注**|可选填，填入该策略的备注信息。|
        |**配置模式**|选择**脚本配置**，支持更大的配置自由度。|
        |**策略内容**|填入下方的自定义权限策略信息。该权限策略通过授予RAM用户刷新和预热接口的权限，使被授权的RAM用户拥有刷新预热功能的权限，可进行刷新预热配置。        ```
{
  "Version": "1",
  "Statement": [
    {
      "Action": [
        "cdn:PushObjectCache",
        "cdn:RefreshObjectCaches",
        "cdn:DescribeRefreshTasks",
        "cdn:DescribeRefreshQuota"
      ],
      "Resource": "acs:cdn:*:*:*",
      "Effect": "Allow"
    }
  ]
}
        ```

**说明：**

        -   CDN所有的API都支持授权，如果您需要创建其他自定义权限策略，可根据业务需求，在策略内容中添加其他API，授予RAM用户相关API的权限。关于授权支持的操作（Action），请参见[RAM鉴权](/cn.zh-CN/新版API参考/RAM鉴权.md)。
        -   策略内容需要使用特定的语法结构来表示，用来精确地描述被授权的资源集、操作集以及授权条件。更多信息，请参见[权限策略基本元素](/cn.zh-CN/权限策略管理/权限策略语言/权限策略基本元素.md)和[权限策略语法和结构](/cn.zh-CN/权限策略管理/权限策略语言/权限策略语法和结构.md)。 |

    5.  单击**确定**。

2.  为RAM用户授权。

    1.  登录[RAM控制台](https://ram.console.aliyun.com)。

    2.  在左侧导航栏，选择**人员管理** \> **用户**。

    3.  找到目标RAM用户，单击其**操作**列的**添加权限**。

        ![添加权限](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/7887283261/p283901.png)

    4.  在**添加权限**面板，配置授权信息。

        ![添加自定义权限](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/0140483261/p284024.png)

        |配置项|说明|
        |---|--|
        |**授权应用范围**|选择**整个云账号**，表示对应的权限应用范围为全局权限，不能选择**指定资源组**。|
        |**被授权主体**|系统根据您选择的目标RAM用户已自动填充。|
        |**选择权限**|选择权限为**自定义策略**，在文本框中输入您在[步骤一](#step_dsb_1z0_5lx)中创建的权限策略名称，本文输入AliyunCdnRefresh，并将其添加到**已选择**区域框中。|

    5.  单击**确定**。

    6.  单击**完成**。


[RAM用户登录控制台](/cn.zh-CN/用户管理/登录管理/RAM用户登录控制台.md)

