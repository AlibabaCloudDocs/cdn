# 快速入门FAQ {#concept_265412 .concept}

-   [如何判断CDN是否生效？](#section_fcu_qvu_s1g)
-   [CDN支持泛域名加速吗？](#section_0t3_151_igy)
-   [CDN添加加速域名时是否允许多个帐号添加不同的子域名？](#section_bku_a88_d1h)
-   [回源的CDN节点IP有哪些？](#section_c26_23o_jt8)
-   [CDN添加域名加速时，报错信息为DOMAIN\_OWNER\_CONFLICT是什么原因？](#section_1il_kqh_an7)
-   [回源HOST与源站的区别是什么？](#section_n1b_xgn_1ql)
-   [加速域名审核失败原因是什么？如何重新提交？](#section_knf_0z5_qga)
-   [多个源站的回源策略是什么？](#section_19x_pnf_8k8)
-   [设置回源HOST的作用是什么？](#section_bps_wtg_8a4)
-   [域名如何绑定HOST？](#section_h8a_ifi_9my)

## 如何判断CDN是否生效？ {#section_fcu_qvu_s1g .section}

验证CDN服务是否已经生效，主要有以下几种方法：

-   方法1：通过输入`ping`或`dig`您所添加的加速域名来验证，如果被转向`*.*kunlun*.com`，表示CDN服务已生效。
    -   `ping`

        ![ping](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/221210/156715345747559_zh-CN.png)

    -   `dig`

        ![dig](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/221210/156715345747560_zh-CN.png)

-   方法2：通过nslookup或dig命令，可以查看相应的加速域名访问CDN节点的IP和延时丢包等基本信息。您可以通过CDN控制台的[IP检测工具](https://cdnnext.console.aliyun.com/tool)，查看解析出来的IP是否为CDN节点的IP，如果是，则说明CDN服务已生效。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/221210/156715345757280_zh-CN.png)

-   方法3：您也可以获取对应加速域名资源的response头查看是否有CDN加速对应的节点信息来判断CDN是否生效。

    ![response](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/221210/156715345747562_zh-CN.jpg)


## CDN支持泛域名加速吗？ {#section_0t3_151_igy .section}

泛域名是指利用通配符来做加速域名以实现所有的次级域名加速效果，例如，您添加了`*.test.com`作为加速域名，将`*.test.com`解析至CDN生成的CNAME域名后，则所有`test.com`的次级域名（如`a.test.com`）均支持CDN加速。

**说明：** 泛域名（`*.test.com`）的三级域名（如`b.a.test.com`）不提供加速服务。

阿里云CDN支持泛域名加速。目前支持泛域名加速的加速业务类型如下：

-   [图片小文件](../intl.zh-CN/产品简介/应用场景/图片小文件.md#)
-   [大文件下载](../intl.zh-CN/产品简介/应用场景/大文件下载.md#)
-   [视音频点播](../intl.zh-CN/产品简介/应用场景/视音频点播.md#)

泛域名添加规则：

-   加速域名总长度小于100字节。
-   最多支持三级泛域名（如`*.b.c.com`）。
-   计费方面，泛域名所有次级域名的流量都会和普通域名一样产生费用，资源监控中会将泛域名产生的流量做汇总，单个泛域名加速将按照一个加速域名作计费处理，即不提供单个准确次级域名的计费数据。

注意事项：

-   日志方面，单个泛域名每个时段提供一份日志文件，日志中将包含该泛域名的所有次级域名加速日志信息。
-   刷新或预热缓存时不支持泛域名URL或者泛域名文件夹，支持刷新准确域名的URL和目录。

## CDN添加加速域名时是否允许多个帐号添加不同的子域名？ {#section_bku_a88_d1h .section}

当泛域名（例如`*.abc.com`）没有被添加到任何帐号下时，阿里云CDN支持多个帐号添加不同的子域名。

## 回源的CDN节点IP有哪些？ {#section_c26_23o_jt8 .section}

为了防止源站被攻击，很多客户希望阿里云CDN提供回源的节点IP，然后在源站设置IP白名单，只让CDN回源的节点访问源站。

但是，由于CDN回源时会智能分配节点访问您的源站服务器，回源的节点IP是不固定的，因此不建议您将源站服务器的回源策略设置为固定的节点IP列表，这样可能会发生回源失败的情况。

如果您有特殊业务需求，源站上有安全狗等防护软件确实需要配置白名单，请调用接口[DescribeL2VipsByDomain](../intl.zh-CN/新版API参考/数据监控类接口/DescribeL2VipsByDomain.md#)，获取CDN回源的节点IP列表并添加到您源站服务器的白名单中，以免影响CDN回源获取资源。

## CDN添加域名加速时，报错信息为DOMAIN\_OWNER\_CONFLICT是什么原因？ {#section_1il_kqh_an7 .section}

原因：添加子域名的用户与泛域名所属的用户不是同一个用户。

解决办法：删除泛域名，或者在同一个用户下添加子域名。

## 回源HOST与源站的区别是什么？ {#section_n1b_xgn_1ql .section}

回源HOST决定回源请求访问到该IP上的哪个站点，而源站决定了回源时，请求到哪个IP。 回源HOST与源站的区别如下：

-   示例1：源站是域名

    假设源站的域名是`www.a.com`，回源HOST为`www.b.com`。那么实际回源的是请求到`www.a.com`解析到的IP，对应主机上的站点是`www.b.com`。

-   示例2：源站是IP

    假设源站的IP是1.1.1.1，回源HOST为`www.b.com`。那么实际回源的是1.1.1.1，对应主机上的站点是`www.b.com`。


如问题还未解决，请[提交工单](https://selfservice.console.aliyun.com/ticket/createIndex)。

## 加速域名审核失败原因是什么？如何重新提交？ {#section_knf_0z5_qga .section}

如果您的源站内容不在阿里云，接入的时候需要进行审核，审核失败的原因一般有如下几种情况：

-   无法正常访问或内容不含有任何实质信息
-   游戏私服类
-   传奇类游戏和纸牌类游戏
-   盗版软件等无版权下载网站
-   P2P类金融网站
-   彩票类网站
-   违规医院和药品类网站
-   涉黄、涉毒、涉赌等

详细说明，请参见[使用限制](../intl.zh-CN/产品简介/使用限制.md#)。

查看审核失败具体原因及重新提交审核的方法如下：

1.  登录[CDN控制台](https://cdnnext.console.aliyun.com)。
2.  单击**域名管理**，您可以查看审核不成功的域名，将鼠标移动至状态为**审核未通过**字样右边的图标，您可以查看审核失败的原因。
3.  单击审核失败的域名右侧的**删除**。
4.  调整之前审核失败的原因，然后重新添加域名等待审核即可。

## 多个源站的回源策略是什么？ {#section_19x_pnf_8k8 .section}

阿里云CDN可设置多个IP、源站域名为源站，同时还可以设置各个源站的优先级，优先级包括主和备。

**说明：** 

-   源站健康检查：实行主动四层健康检查机制，测试源站的80端口。每2.5秒检查一次，连续3次失败标记为不可用。
-   设置完成后，CDN回源时将按照设置的多个源站采用轮询的方式进行回源请求。因此，您需要确保各源站对应得站点内容要一致，否则将导致CDN获取到的数据存在差异。

多个源站的回源策略：用户100%回源流量将首先回源优先级为主的源站，如果某个源站健康检查连续3次失败，则100%流量将回源优先级为备的源站。如果主动健康检查成功，那么该源站将重新标记为可用，恢复原来优先级。当所有源站的回源优先级相同时，CDN将自动轮询回源。

## 设置回源HOST的作用是什么？ {#section_bps_wtg_8a4 .section}

如果CDN后端用户的的源站web服务上没有绑定加速域名，只绑定了其他域名，未限制域名访问（例如通过服务器IP可以访问到默认网站），那么您可以通过CDN控制台设置回源HOST，这样web服务器上可以在未绑定加速域名的情况下使用CDN服务。

示例：假设您的服务器上只绑定了`test.abc.com`，没有绑定`cdn.abc.com`，那么您只需要在回源HOST中填写`test.abc.com`即可访问。

测试验证

1.  使用curl命令访问服务器`127.0.0.1`，未返回服务器中网站的正常内容，说明源站可能是绑定了域名或者对域名访问进行了限制，无法直接打开网站。
2.  使用`-H`参数将加速域名`cdn.abc.com`传递测试，也不能打开网站，说明web源站上没有绑定加速域名。
3.  使用`-H`参数将`test.abc.com`传递，可以正常打开网站，说明源站绑定了该域名。同时在CDN控制台设置了回源HOST为`test.abc.com`后，经测试，`cdn.abc.com`可以打开。

    ![host](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/221210/156715345747728_zh-CN.jpg)


## 域名如何绑定HOST？ {#section_h8a_ifi_9my .section}

您可以在不修改域名解析的情况下绑定HOST，域名指定特定IP，对比加速与未加速的访问效果。

具体操作如下：

1.  在C:\\Windows\\System32\\drivers\\etc目录下打开hosts文件。
2.  输入IP地址+空格+您的域名。

    ![host](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/221210/156715345747729_zh-CN.png)

    此时，如果您运行`ping www.test.com`，那么解析指向的IP为`1.1.1.1`。

    **说明：** window解析常识：在浏览器访问域名时，首先从DNS缓存，host文件获取域名对应IP，如果都没有，才会用本地DNS获取域名解析指向的IP，详细说明您可以自行查阅相关文档。


示例：您的域名`www.test.com`使用了CDN加速服务，当您打开`www.test.com`时访问错误，但是又不方便修改域名解析，此时您可以通过修改本地host文件解决该问题。

如果修改host IP为源站服务器后，打开报错，说明源站出错，不在CDN上。如果修改host IP为源站服务器后打开正常，CDN加速域名打开有问题，可以对比一下两个链接，如果CDN开启过滤参数，会过滤掉URL中`？`后面的参数，例如访问`www.test.com`实际打开的是`www.test.com/?***=**`，实际打开CDN加速域名`?***=**`会被过滤掉，关闭过滤参数即可。

