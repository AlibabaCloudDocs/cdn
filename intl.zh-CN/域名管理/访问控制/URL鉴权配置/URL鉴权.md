---
keyword: [鉴权, CDN, 访问控制]
---

# URL鉴权

URL鉴权功能主要用于保护用户站点的资源不被非法站点下载盗用。通过防盗链方法添加Referer黑名单和白名单的方式可以解决一部分盗链问题，由于Referer内容可以伪造，所以Referer防盗链方式无法彻底保护站点资源。因此，您可以采用URL鉴权方式保护源站资源更为安全有效。

URL鉴权功能通过阿里云CDN加速节点与客户资源站点配合，形成了更为安全可靠的源站资源防盗方法。

-   CDN客户站点提供加密URL，URL中包含权限验证信息。
-   用户使用加密后的URL向加速节点发起请求。
-   加速节点对加密URL中的权限信息进行验证，判断请求的合法性。正常响应合法请求，拒绝非法请求。

如果您想了解Python鉴权代码示例，请参见 [鉴权示例](/intl.zh-CN/域名管理/访问控制/URL鉴权配置/鉴权示例.md)。

**说明：** 您的请求URL经过CDN鉴权后，URL中的特殊字符，例如`=`、`+`等会被转义。

1.  登录[CDN控制台](https://cdn.console.aliyun.com)。

2.  在左侧导航栏，单击**域名管理**。

3.  在**域名管理**页面，单击目标域名对应的**管理**。

4.  在指定域名的左侧导航栏，单击**访问控制**。

5.  单击**URL鉴权**页签。

6.  在**鉴权URL设置**区域，单击**修改配置**。

7.  打开**URL鉴权**开关，配置URL鉴权信息。

    ![URL鉴权](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/9731090261/p64280.png)

    |参数|说明|
    |--|--|
    |**鉴权类型**|阿里云CDN兼容并支持三种鉴权方式。您可以根据访问加密URL格式，选择合适的鉴权方式，来实现对源站资源的有效保护。URL鉴权类型如下：

    -   [鉴权方式A说明](/intl.zh-CN/域名管理/访问控制/URL鉴权配置/鉴权方式A说明.md)
    -   [鉴权方式B说明](/intl.zh-CN/域名管理/访问控制/URL鉴权配置/鉴权方式B说明.md)
    -   [鉴权方式C说明](/intl.zh-CN/域名管理/访问控制/URL鉴权配置/鉴权方式C说明.md)
**说明：** URL鉴权错误都会返回403报错：

    -   MD5计算类错误

例如：`X-Tengine-Error:denied by req auth: invalid md5hash=de7bfdc915ced05e17380a149bd760be`

    -   时间类报错

例如：`X-Tengine-Error:denied by req auth: expired timestamp=1439469547` |
    |**主KEY**|输入鉴权方式对应的主用密码。|
    |**备KEY**|输入鉴权方式对应的备用密码。|

8.  单击**确定**。


生成鉴权URL的操作方法如下：

1.  在**生成鉴权URL**区域，配置**原始URL**和鉴权信息。

    |参数|说明|
    |--|--|
    |**原始URL**|您可以输入完整的原始URL地址，例如：`https://www.aliyun.com`。|
    |**鉴权类型**|您可以根据所需，选择合适的URL鉴权类型：

    -   [鉴权方式A说明](/intl.zh-CN/域名管理/访问控制/URL鉴权配置/鉴权方式A说明.md)
    -   [鉴权方式B说明](/intl.zh-CN/域名管理/访问控制/URL鉴权配置/鉴权方式B说明.md)
    -   [鉴权方式C说明](/intl.zh-CN/域名管理/访问控制/URL鉴权配置/鉴权方式C说明.md) |
    |**鉴权KEY**|您可以根据所需，设置鉴权密码。**鉴权KEY**是**鉴权URL设置**中配置的**主KEY**或**备KEY**。|
    |**有效时间**|您可以根据所需，设置URL鉴权的有效时长。单位为：秒，例如：1800。**说明：** CDN鉴权的有效时间默认为30分钟，如果您想使链接生成的有效时间小于30分钟，需要将**有效时间**设置为负数。例如，您想设置链接有效时间为10s，则需要设置**有效时间**为-1790s。 |

    ![生成鉴权URL](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4798068951/p64282.png)

2.  单击**开始生成**。

    获得**鉴权URL**和**Timestamp**。

    ![URL鉴权](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4798068951/p50938.png)


