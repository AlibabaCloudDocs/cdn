# 限制RAM用户修改计费模式

如果您需要限制RAM用户修改计费模式，可以通过访问控制RAM（Resource Access Management）的自定义策略实现。通过本文，您可以了解限制RAM用户修改计费模式的操作方法。

阿里云CDN提供了RAM用户来实现不同业务之间的隔离操作，被赋予AliyunCDNFullAccess（管理CDN）权限的RAM用户默认拥有数据查看、域名功能管理和计费模式修改的权限。如果您需要限制RAM用户修改计费模式的权限，同时保留其他权限，可通过访问控制RAM自定义策略来实现。查看RAM用户权限，请参见[查看RAM用户的权限](/cn.zh-CN/用户管理/授权管理/查看RAM用户的权限.md)。

1.  创建自定义权限策略。

    1.  使用阿里云账号登录[RAM控制台](https://signin.aliyun.com/1212365956692947.onaliyun.com/login.htm?callback=https%3A%2F%2Fram.console.aliyun.com%2F&accounttraceid=d5ca38cd6caf4a98932e70596631ed7codid&cspNonce=Gn0uvC6Rz7&oauth_callback=https%3A%2F%2Fram.console.aliyun.com%2F&spma=a2c44&spmb=11131515#/main)。
    2.  在左侧导航栏，选择**权限管理** \> **权限策略管理**。
    3.  在**权限策略管理**页面，单击**创建权限策略**。
    4.  在**新建自定义权限策略**页面，输入**策略名称**和**备注**。

        ![新建自定义权限策略](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/3497993261/p284575.png)

        |配置项|说明|
        |---|--|
        |**策略名称**|填入具备业务意义的名称以便后续识别。（例如：限制RAM用户修改计费模式）|
        |**备注**|（选填）填入该策略的备注信息。|
        |**配置模式**|选择**脚本配置**，限制RAM用户修改计费模式的脚本内容如下：

        ```
{
    "Version": "1",
    "Statement": [
        {
            "Action": [
                "ram:GetPolicy",
                "ram:AttachPolicyToRole"
            ],
            "Resource": [
                "acs:ram:*:*:*/AliyunCDNLoggingRolePolicy",
                "acs:ram:*:*:*/AliyunCDNAccessingPrivateOSSRolePolicy",
                "acs:ram:*:*:*/AliyunCDNLogArchiveRolePolicy",
                "acs:ram:*:*:*/AliyunCDNEventNotificationRolePolicy",
                "acs:ram:*:*:*/AliyunCDNAccessingPrivateOSSRole"
            ],
            "Effect": "Allow"
        },
        {
            "Action": [
                "ram:CreateRole"
            ],
            "Resource": [
                "*"
            ],
            "Effect": "Allow"
        }
    ]
}
        ```

**说明：**

        -   脚本中关于`Action`或`Resource`的使用规则，请参见[权限策略基本元素](/cn.zh-CN/权限策略管理/权限策略语言/权限策略基本元素.md)。
        -   您还可以选择**可视化配置**，系统预置了**添加授权语句**，通过不同选项来实现权限配置。 |
        |**策略内容**|填入具体的权限策略信息。|

    5.  单击**确定**。
2.  为RAM用户授权。

    1.  使用阿里云账号登录[RAM控制台](https://signin.aliyun.com/1212365956692947.onaliyun.com/login.htm?callback=https%3A%2F%2Fram.console.aliyun.com%2F&accounttraceid=d5ca38cd6caf4a98932e70596631ed7codid&cspNonce=Gn0uvC6Rz7&oauth_callback=https%3A%2F%2Fram.console.aliyun.com%2F&spma=a2c44&spmb=11131515#/main)。
    2.  （可选）创建RAM用户，详细操作步骤请参考[创建RAM用户](/cn.zh-CN/用户管理/基本操作/创建RAM用户.md)。

        **说明：** 如果您已经创建了RAM用户，可跳过该步骤。

    3.  在左侧导航栏，选择**人员管理** \> **用户**。
    4.  选择目标RAM用户，单击操作列的**添加权限**。
    5.  在添加权限面板，配置授权信息。

        ![添加权限](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/3497993261/p284519.png)

        |配置项|说明|
        |---|--|
        |**授权应用范围**|选择**整个云账号**，表示对应的权限应用范围为全局权限。 |
        |**被授权主体**|系统根据您上一步选择的目标RAM用户，已自动匹配填写。|
        |**选择权限**|选择**自定义策略**，找到您在[创建自定义权限策略](#step_p1e_k73_sfs)中已经创建的策略名称（例如：限制RAM用户修改计费模式），单击该策略名称，将其添加到已选择区域框中。 |

    6.  单击**确定**。
    7.  单击**完成**。

