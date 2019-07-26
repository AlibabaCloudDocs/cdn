# 配置HTTPS证书 {#task_261642 .task}

阿里云CDN仅支持PEM格式的证书和私钥，您需要上传HTTPS证书至CDN，开启HTTPS安全加速。本文档介绍了不同类型的HTTPS证书的认证方式和配置方法。

配置HTTPS证书前，您需要先购买证书，您可以在[云盾控制台](https://yundun.console.aliyun.com/?spm=5176.8232292.domaindetail.24.9498142fSMfoJd&p=cas#/cas/home)快速申请免费的证书或购买高级证书。

根据证书认证级别分类如下：

-   DV是Domain Validation，仅认证域名所有权，通常是验证域名下指定文件内容，或者验证与域名相关TXT记录，显示明显的安全锁。
-   OV是Organization Validation，验证企业组织真实性的标准型SSL证书，比DV SSL证书更安全可信，审核更严格，审核周期也更长。一般多用于电商，教育，游戏等领域。
-   EV是Extended Validation，CA/browser forum指定的全球统一标准，通过证书object identifier（OID）来识别，显示完整企业名称，是目前全球最高等级的SSL证书，多用于金融支付，网上银行等领域。

**说明：** 目前CDN仅支持`PEM`格式的证书，如果您的证书不是PEM格式，请进行格式转换，操作方法请参见[证书格式转换方式](cn.zh-CN/域名管理/HTTPS安全加速/证书格式说明.md#section_cn2_rql_xdb)。

1.  登录[CDN控制台](https://cdnnext.console.aliyun.com)。
2.  在左侧导航栏，单击**域名管理**。
3.  在域名管理界面，单击目标域名后的**管理**。
4.  在左侧导航栏，单击**HTTPS配置**。
5.  在HTTPS证书界面，单击**修改配置**。 

    ![HTTPS证书](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5134/156414061711410_zh-CN.png)

6.  在HTTPS设置界面，打开**HTTPS安全加速**开关，配置证书相关参数。 

    当您打开HTTPS安全加速开关时，系统弹出确认开启HTTPS界面，该操作单独计费，您可以根据所需选择是否开启。HTTPPS计费标准请参考[增值服务计费](../../../../cn.zh-CN/产品定价/计费方式/增值服务计费.md#)。

    |参数|说明|
    |--|--|
    |证书类型|     -   云盾

您可以在[云盾控制台](https://yundun.console.aliyun.com/?spm=5176.8232292.domaindetail.24.9498142fSMfoJd&p=cas#/cas/home)快速申请免费的证书或购买高级证书。

    -   自定义

如果证书列表中无当前适配的证书，您可以选择自定义上传。您需要在设置证书名称后，上传证书内容和私钥，该证书将会在阿里云云盾的证书服务中保存。您可以在[我的证书](https://yundun.console.aliyun.com/?spm=5176.2020520110.all.12.16df56a1u1IhI6&p=cas#/cas/home)里查看。

    -   免费证书

阿里云的Digicert免费型DV版SSL证书。CDN的免费证书只适用于CDN的HTTPS安全加速业务，因此您无法在阿里云云盾控制台管理该证书，也无法查看到公钥和私钥。

        -   免费证书的申请需要5~10分钟。等待期间，您也可以重新选择上传自定义证书或云盾证书。
        -   免费证书有效期为1年，到期后自动续签。
        -   在您使用过程中，如果关闭HTTPS安全加速，当再次开启使用免费证书时，将直接使用已申请但未过期的证书。若开启时证书已过期，您需要重新申请免费证书。
 云盾证书、自定义证书和免费证书之间可以相互切换。

 |
    |证书名称|当**证书类型**选择**云盾**或**自定义**时，需要配置证书名称。|
    |内容|当**证书类型**选择**自定义**时，需要配置该参数。配置方法请参考**内容**输入框下方的**pem编码参考样例**。|
    |私钥|当**证书类型**选择**自定义**时，需要配置该参数。配置方法请参考**私钥**输入框下方的**pem编码参考样例**。|

    ![修改HTTPS证书](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5134/156414061811413_zh-CN.png)

7.  单击**确认**。 

    您可以停用、启用和修改证书。停用证书后，系统将不再保留证书信息。再次开启证书时，需要重新上传证书或私钥。

8.  验证证书是否生效。 

    更新HTTPS证书1分钟后全网生效，使用HTTPS方式访问资源，如果浏览器中出现绿色HTTPS标识，则HTTPS安全加速生效。

    ![验证结果](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5134/15641406183701_zh-CN.png)


