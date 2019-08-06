# CDN子账户使用指南 {#task_261642 .task}

如果您需要对CDN域名进行分组管理，则可以通过子账户和资源组授权的方式实现不同部门之间资源的隔离操作。通过本文您可以了解创建CDN子账号，以及为其授权的操作方法。

1.  使用主账户登录[企业控制台](https://enterprise.console.aliyun.com/)。 

    企业控制台的操作方法，请参见[企业控制台使用手册](https://help.aliyun.com/document_detail/59910.html)。

    **说明：** 在企业控制台设置好子账户相应的资源组和权限后，您使用子账户登录CDN控制台，只能按照设置的规则进行有限的资源查看和操作，保证子账户之间的操作和资源展示完全隔离。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5176/15650825903487_zh-CN.png)

2.  创建子账户。 
    1.  在企业控制台的左侧导航栏，选择**人员目录** \> **用户管理**。 

        根据业务需求，您还可以通过群组管理功能创建群组，统一管理子账户。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5176/15650825903488_zh-CN.png)

        **说明：** 当您首次进入人员目录时，需要创建目录，一个用户只能归属于一个目录。

    2.  在用户管理界面，单击**创建内部人员**。 

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5176/156508259151346_zh-CN.png)

    3.  根据界面提示，配置子账户信息。
    4.  单击**确定**。
3.  创建资源组。 
    1.  在企业控制台的左侧导航栏，选择**资源管理**。 

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5176/156508259151347_zh-CN.png)

    2.  在资源组管理界面，单击**新建资源组**。 

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5176/156508259151349_zh-CN.png)

    3.  根据界面提示，配置资源组信息。
    4.  单击**确定**。
4.  资源组添加资源。 
    1.  单击新创建资源组对应的**资源管理**。 

        ![资源管理](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5176/156508259154431_zh-CN.png)

    2.  在资源管理页签，选择产品类型为CDN。
    3.  选择需要加入该资源组的加速域名，单击**转入资源** 。
    4.  单击**确定**。
5.  子账户授权。 
    1.  单击新创建资源组对应的**权限管理**。
    2.  在权限管理页签，单击**新增授权**。 

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5176/156508259151353_zh-CN.png)

    3.  根据界面提示，选择需要赋权的子账户和权限。 

        给子账户赋予管理CDN的权限AliyunCDNFullAccess。

        当前RAM模板策略如下：

        -   AliyunCDNFullAccess：CDN管理授权。支持增加、修改、删除和查看。

            ``` {#codeblock_9gg_mw3_rw7}
            {
              "Version": "1",
              "Statement": [
                {
                  "Action": "cdn:*",
                  "Resource": "*",
                  "Effect": "Allow"
                }
              ]
            }
            ```

        -   AliyunCDNReadOnlyAccess：CDN只读权限。

            ``` {#codeblock_3n6_4xn_m6z}
            {
              "Version": "1",
              "Statement": [
                {
                  "Action": "cdn:Describe*",
                  "Resource": "*",
                  "Effect": "Allow"
                }
              ]
            }
            ```

    4.  单击**确定**。
6.  使用子账号登录CDN控制台。 

    登录地址： [http://signin.aliyun.com/自定义域.onaliyun.com/login.htm](http://signin.aliyun.com/%3C%E8%87%AA%E5%AE%9A%E4%B9%89%E5%9F%9F%3E.onaliyun.com/login.htm)。

    子账户登录后，可以选择展示当前子账户拥有权限的资源组，根据资源组罗列加速域名。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5176/15650825923493_zh-CN.png)

    CDN子账户不支持图片鉴黄，其他功能的操作方法与主账号完全相同，请参见[域名管理](../DNCDN11828177/ZH-CN_TP_5118_V15.dita#concept_tvm_vhx_wdb)和[服务管理](ZH-CN_TP_1162242_V1.dita#concept_1461607)。


