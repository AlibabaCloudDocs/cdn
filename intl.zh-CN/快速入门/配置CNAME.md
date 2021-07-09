---
keyword: [CNAME, 万网CNAME接入CDN, 万网CNAME解析, 阿里云域名CNAME]
---

# 配置CNAME

成功添加加速域名后，系统会为您分配一个CNAME域名。您需要在域名解析服务商处完成CNAME配置，将加速域名的DNS解析记录指向CNAME域名，您的访问请求才能转发到CDN节点，待CNAME配置生效后，CDN才能真正实现加速。配置过程中如果CNAME记录与A记录冲突，您需要将A记录修改为CNAME记录。

## 配置CNAME方法汇总

配置CNAME需要在域名所在的DNS解析服务商完成。本文为您介绍在阿里云、腾讯云和新网配置CNAME的方法，在其他域名服务商配置CNAME的方法与本文介绍的方法类似。

-   如果您的域名是在阿里云，请参见[阿里云配置CNAME流程](#section_pbv_cbm_ipp)。
-   如果您的域名是在腾讯云，请参见[腾讯云配置CNAME流程](#section_1bd_hlb_5w4)。
-   如果您的域名是在新网，请参见[新网配置CNAME流程](#section_z5s_mcc_0cq)。

## 阿里云配置CNAME流程

如果您的DNS服务商是阿里云，您可以根据以下步骤完成CNAME配置。

1.  获取加速域名的CNAME地址。

    1.  登录[CDN控制台](https://cdn.console.aliyun.com)。

    2.  在左侧导航栏，单击**域名管理**。

    3.  在**域名管理**页面，复制加速域名对应的CNAME地址。

        ![域名管理](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/9618134161/p66555.png)

2.  添加CNAME记录。

    1.  登录[云解析DNS控制台](https://dns.console.aliyun.com)。

    2.  在**域名解析**页面，找到您的域名，在域名右侧单击**解析设置**。

    3.  单击**添加记录**，添加CNAME记录。

        **说明：**

        -   精准域名的CNAME解析优先级大于泛域名的CNAME解析。如果您的加速域名为泛域名，且主机记录设置为星号（\*）时，需删除泛域名下所有已生效的二级域名的解析记录。
        -   添加CNAME记录时如果遇到冲突问题，建议您更换一个加速域名或调整冲突的记录。
        ![添加记录](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/5843918061/p64412.png)

        |参数|说明|填写样例|
        |--|--|----|
        |**记录类型**|选择CNAME。|CNAME|
        |**主机记录**|主机记录指加速域名的前缀。|        -   加速域名为`testcdn.aliyun.com`，主机记录为`testcdn`。
        -   加速域名为`www.aliyun.com`，主机记录为`www`。
        -   加速域名为`aliyun.com`，主机记录为`@`。
        -   加速域名为`*.aliyun.com`，主机记录为`*`。 |
        |**解析线路**|默认线路。|保持默认|
        |**记录值**|输入加速域名对应的CNAME地址。

**说明：** 一个加速域名对应一个CNAME地址，二级域名不能使用主域名的CNAME地址。如果您要加速二级域名，需要将二级域名也添加到CDN上并解析到对应的CNAME地址，或者在CDN上添加泛域名，泛域名的CNAME可以被二级域名使用。添加泛域名或二级域名，请参见[添加加速域名](/intl.zh-CN/快速入门/添加加速域名.md)。

|all.example.com.w.kunlunsl.com|
        |**TTL**|TTL为缓存时间，数值越小，修改记录后各地生效时间越快，默认为10分钟。|保持默认|

    4.  单击**确认**，完成添加。

        成功配置CNAME且生效后加速服务会立即生效。新增CNAME记录实时生效，修改CNAME记录在10分钟后生效（具体生效时间长短取决于域名DNS解析配置的TTL时长，10分钟为TTL的默认时长）。成功配置CNAME后状态更新约有10分钟延迟，CDN控制台的域名列表中可能仍显示“未配置CNAME”，请先忽略。

3.  验证CNAME配置是否生效。

    1.  打开Windows操作系统中的cmd程序。

    2.  在命令行中ping加速域名，如果返回的解析结果和CDN控制台上该加速域名的CNAME值一致，则表示CDN加速已经生效。

        ![CNAME生效验证](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/9618134161/p66693.png)


## 腾讯云配置CNAME流程

如果您的DNS服务商是腾讯云，您可以根据以下步骤完成CNAME配置。

1.  获取加速域名的CNAME地址。

    1.  登录[CDN控制台](https://cdn.console.aliyun.com)。

    2.  在左侧导航栏，单击**域名管理**。

    3.  在**域名管理**页面，复制加速域名对应的CNAME地址。

        ![域名管理](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/9618134161/p66555.png)

2.  添加CNAME记录。

    1.  登录DNSPod控制台。

    2.  在对应域名的域名解析页，单击**添加记录**，添加CNAME记录。

        |参数|说明|填写样例|
        |--|--|----|
        |**主机记录**|主机记录指加速域名的前缀。|        -   加速域名为`testcdn.aliyun.com`，主机记录为`testcdn`。
        -   加速域名为`www.aliyun.com`，主机记录为`www`。
        -   加速域名为`aliyun.com`，主机记录为`@`。
        -   加速域名为`*.aliyun.com`，主机记录为`*`。 |
        |**记录类型**|选择CNAME。|CNAME|
        |**线路类型**|选择“默认”类型。|保持默认|
        |**记录值**|输入加速域名对应的CNAME地址。

**说明：** 一个加速域名对应一个CNAME地址，二级域名不能使用主域名的CNAME地址。如果您要加速二级域名，需要将二级域名也添加到CDN上并解析到对应的CNAME地址，或者在CDN上添加泛域名，泛域名的CNAME可以被二级域名使用。添加泛域名或二级域名，请参见[添加加速域名](/intl.zh-CN/快速入门/添加加速域名.md)。

|all.example.com.w.kunlunsl.com|
        |**权重**|无需填写。|不涉及|
        |**MX**|无需填写。|不涉及|
        |**TTL**|TTL为缓存时间，数值越小，修改记录后各地生效时间越快。|保持默认|

    3.  单击**保存**，完成添加。

        成功配置CNAME且生效后加速服务会立即生效。成功配置CNAME后状态更新约有10分钟延迟，CDN控制台的域名列表中可能仍显示“未配置CNAME”，请先忽略。

3.  验证CNAME配置是否生效。

    1.  打开Windows操作系统中的cmd程序。

    2.  在命令行中ping加速域名，如果返回的解析结果和CDN控制台上该加速域名的CNAME值一致，则表示CDN加速已经生效。

        ![CNAME生效验证](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/9618134161/p66693.png)


## 新网配置CNAME流程

如果您的DNS服务商是新网，您可以根据以下步骤完成CNAME配置。

1.  获取加速域名的CNAME地址。

    1.  登录[CDN控制台](https://cdn.console.aliyun.com)。

    2.  在左侧导航栏，单击**域名管理**。

    3.  在**域名管理**页面，复制加速域名对应的CNAME地址。

        ![域名管理](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/9618134161/p66555.png)

2.  添加CNAME记录。

    1.  登录新网域名解析控制台。

    2.  在对应域名的域名解析页，单击**添加新的别名**，添加CNAME记录。

        |参数|说明|填写样例|
        |--|--|----|
        |**别名**|需指向的域名，即CDN为您分配的CNAME域名。**说明：** 一个加速域名对应一个CNAME地址，二级域名不能使用主域名的CNAME地址。如果您要加速二级域名，需要将二级域名也添加到CDN上并解析到对应的CNAME地址，或者在CDN上添加泛域名，泛域名的CNAME可以被二级域名使用。添加泛域名或二级域名，请参见[添加加速域名](/intl.zh-CN/快速入门/添加加速域名.md)。

|all.example.com.w.kunlunsl.com|
        |**别名主机**|别名主机指加速域名的前缀。|        -   加速域名为`testcdn.aliyun.com`，别名主机为`testcdn`。
        -   加速域名为`www.aliyun.com`，别名主机为`www`。
        -   加速域名为`aliyun.com`，别名主机为`@`。
        -   加速域名为`*.aliyun.com`，别名主机为`*`。 |
        |**TTL**|TTL为缓存时间，数值越小，修改记录后各地生效时间越快。|保持默认|

    3.  单击**提交**，完成添加。

        成功配置CNAME且生效后加速服务会立即生效。成功配置CNAME后状态更新约有10分钟延迟，CDN控制台的域名列表中可能仍显示“未配置CNAME”，请先忽略。

3.  验证CNAME配置是否生效。

    1.  打开Windows操作系统中的cmd程序。

    2.  在命令行中ping加速域名，如果返回的解析结果和CDN控制台上该加速域名的CNAME值一致，则表示CDN加速已经生效。

        ![CNAME生效验证](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/9618134161/p66693.png)


## 后续步骤

-   配置缓存规则：CDN默认缓存时间为3600秒，您可以修改缓存时间。设置的缓存时间长短会导致回源流量不一样，回源费用也有所不同，建议根据不同的业务需求设置缓存时长。设置的缓存时间过短，会导致CDN频繁回源，从而增加源站的流量消耗。详细信息，请参见[配置缓存过期时间](/intl.zh-CN/域名管理/缓存配置/配置缓存过期时间.md)。
-   提高缓存命中率：使用CDN加速后如果缓存命中率低，您可以配置预热功能，在业务高峰前提前预热热门资源。详细信息，请参见[预热资源](/intl.zh-CN/服务管理/刷新和预热资源.md)。

