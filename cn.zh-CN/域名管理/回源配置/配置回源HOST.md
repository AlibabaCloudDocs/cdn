---
keyword: [回源HOST, CDN节点回源]
---

# 配置回源HOST

如果您需要自定义CDN节点回源时需要访问的具体服务器域名，则需要配置回源HOST的域名类型。回源HOST可选域名类型包括：加速域名、源站域名和自定义域名。

回源HOST指CDN节点在回源过程中，在源站访问的站点域名。当您的源站有多个业务共用的情况时，可以通过用户回源的HTTP请求头中携带的HOST信息来区分不同的业务。

**说明：**

-   如果您的源站绑定了多个域名或站点，则需要在回源HOST中，指定具体域名，否则回源会失败。
-   如果您的加速域名是泛域名，且回源协议为HTTP协议，则需要在回源HOST中，指定具体域名，否则回源会失败。

源站和回源HOST的区别：

-   源站：源站决定了回源时请求到的具体IP地址。
-   回源HOST：回源HOST决定了回源请求访问到该IP地址上的具体站点。

1.  登录[CDN控制台](https://cdn.console.aliyun.com)。

2.  在左侧导航栏，单击**域名管理**。

3.  在**域名管理**页面，单击目标域名对应的**管理**。

4.  在指定域名的左侧导航栏，单击**回源配置**。

5.  在**回源HOST**区域，单击**修改配置**。

6.  打开**回源HOST**开关，选择**域名类型**。

    ![回源配置](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/0664788951/p64119.png)

    |参数|说明|
    |--|--|
    |**加速域名**|加速域名是指您需要加速的域名，即终端用户直接访问到的域名。例如：加速域名为`cdntest.com`。当回源HOST的域名类型选择为**加速域名**的时候，回源HOST将会被配置为加速域名`cdntest.com`。 |
    |**源站域名**|源站域名是指您的源站服务器的域名地址，即CDN回源需要访问的域名地址。例如：源站域名为`origin.com`。当回源HOST的域名类型选择为**源站域名**的时候，回源HOST将会被配置为源站域名`origin.com`。 |
    |**自定义域名**|当回源HOST的域名类型选择为**自定义域名**的时候，回源HOST将会被配置为用户指定的任意域名。例如：如果您的源站绑定了多个域名，则需要指定具体域名，否则回源会失败。 |

7.  单击**确定**。


**样例一：**当源站类型为域名。

|功能状态|域名|说明|
|----|--|--|
|回源HOST功能关闭|加速域名：`cdntest.com`

源站地址：

`origin.com`

|-   域名类型选择**加速域名**，则回源HOST为`cdntest.com`。
-   域名类型选择**源站域名**，则回源HOST为`origin.com`。
-   域名类型选择**自定义域名**，则回源HOST为用户输入的自定义域名。 |

**样例二：**当源站类型为IP地址。

|功能状态|域名|说明|
|----|--|--|
|回源HOST功能关闭|加速域名：`cdntest.com`

源站地址：

`1.1.1.1`

|-   域名类型选择**加速域名**，则回源HOST为`cdntest.com`。
-   域名类型选择“**自定义域名**，则回源HOST为用户输入的自定义域名。

**说明：** 源站地址是IP地址类型，所以域名类型的**源站域名**选项被置灰，不可选择。 |

**样例三：**当源站类型为OSS域名。

|功能状态|域名|说明|
|----|--|--|
|回源HOST功能开启|加速域名：`cdntest.com`

源站地址：

`test.oss-cn-hangzhou.aliyuncs.com`

|-   域名类型选择**加速域名**，则回源HOST为`cdntest.com`。
-   域名类型选择**源站域名**，则回源HOST为`test.oss-cn-hangzhou.aliyuncs.com`。
-   域名类型选择**自定义域名**，则回源HOST为用户输入的自定义域名。

**说明：** 在源站地址被配置为OSS类型的时候，将会同步开启回源HOST功能，并且按以下配置来设置回源HOST：：

域名类型：源站域名

域名地址：`test.oss-cn-hangzhou.aliyuncs.com` |

**相关文档**  


[批量配置域名](/cn.zh-CN/新版API参考/域名管理类接口/批量配置域名.md)

