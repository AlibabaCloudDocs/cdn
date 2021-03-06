# 配置回源HTTP响应头

当您需要改写用户回源响应请求URL中的HTTP Header时，可以配置功能。通过本文，您可以了解配置回源HTTP响应头功能的操作步骤。

HTTP消息头是指，在超文本传输协议HTTP（Hypertext Transfer Protocol）的请求和响应消息中，协议头部的组件。

在HTTP消息头中，按其出现的上下文环境，分为通用头、请求头、响应头等。

![回源响应](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6764788951/p88049.png)

**说明：**

-   回源请求是指用户请求中该加速域名下有通过CDN返回源站的HTTP消息。
-   回源HTTP响应头的配置只会影响通过CDN回源的HTTP消息，对于CDN节点直接响应给用户的HTTP消息不做修改。
-   目前不支持泛域名设置。

1.  登录[CDN控制台](https://cdn.console.aliyun.com)。

2.  在左侧导航栏，单击**域名管理**。

3.  在**域名管理**页面，单击目标域名对应的**管理**。

4.  在指定域名的左侧导航栏，单击**回源配置**。

5.  单击**回源HTTP响应头**页签。

6.  单击**添加**。

7.  配置回源HTTP响应头信息。

    **说明：** 当不同的操作方式同时作用于同一个回源响应头参数的时候，将会存在操作冲突的情况。此时按照操作类型的优先级来执行，优先级顺序为**替换** \> **增加** \> **变更、删除**。

    例如：当增加和删除操作同时作用于同一个参数时，会先增加，再删除。

    -   增加响应头参数

        ![HTTP响应头](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/7969769161/p88069.png)

        |配置项|示例|说明|
        |---|--|--|
        |响应头操作|增加|在回源HTTP请求中增加指定的响应头参数。|
        |自定义响应头参数|自定义缓存响应头|可以选择在配置弹窗中已经预制的响应头参数，也可以在下拉框里选择**自定义缓存响应头**，配置自定义响应头参数。|
        |自定义响应头名称|x-code|自定义响应头名称为x-code。|
        |响应头值|key1|一个响应头参数里面，可以配置多个值，不同值之间使用英文逗号（,）分隔。|
        |key1，key2|
        |是否允许重复|允许|当**是否允许重复**设置为**允许**时，可以添加重复的响应头参数。例如：`x-code:key1`，`x-code:key2`。|
        |不允许|当**是否允许重复**设置为**不允许**时，添加同一个响应头参数，后面添加的值会覆盖前面添加的值。例如：先添加`x-code:key1`后，再添加`x-code:key2`，最终的值为`x-code:key2`。|

    -   删除响应头参数

        ![删除](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8969769161/p88647.png)

        |配置项|示例|说明|
        |---|--|--|
        |响应头操作|删除|删除所有与响应头参数名称匹配的参数值，无论是否有重复的响应头参数。|
        |自定义响应头参数|自定义缓存响应头|可以选择在配置弹窗中已经预制的响应头参数，也可以在下拉框里选择**自定义缓存响应头**，删除自定义响应头参数。|
        |自定义响应头名称|x-code|自定义响应头名称为x-code。|

    -   变更响应头参数

        ![变更](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8969769161/p88648.png)

        |配置项|示例|说明|
        |---|--|--|
        |响应头操作|变更|当响应头参数不存在重复时，可以正常变更参数，有多个重复响应头参数的情况下，不允许进行变更操作。|
        |自定义响应头参数|自定义缓存响应头|可以选择在配置弹窗中已经预制的响应头参数，也可以在下拉框里选择**自定义缓存响应头**，变更自定义响应头参数。|
        |自定义响应头名称|x-code|自定义响应头名称为x-code。|
        |响应头变更为|key1，key3|一个响应头参数里面，可以配置多个值，不同值之间使用英文逗号（,）分隔。|

    -   替换响应头参数

        ![替换](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8969769161/p88654.png)

        |配置项|示例|说明|
        |---|--|--|
        |响应头操作|替换|当响应头参数不存在重复时，可以正常替换参数，有多个重复响应头参数的情况下，不允许进行替换操作。|
        |自定义响应头参数|自定义缓存响应头|可以选择在配置弹窗中已经预制的响应头参数，也可以在下拉框里选择**自定义缓存响应头**，变更自定义响应头参数。|
        |自定义响应头名称|x-code|自定义响应头名称为x-code。|
        |查找|key|正则表达式查找需要替换的参数值。|
        |替换为|abc|正则表达式替换需要替换的参数值。|
        |匹配|匹配所有|当**匹配**选项设置为**匹配所有**时，所有被匹配的值都会被替换。例如：`x-code:key1,key2,key3`，正则匹配值key替换为abc，替换后的结果为`x-code:abc1,abc2,abc3`。|
        |仅匹配第一个|当**匹配**选项设置为**仅匹配第一个**时，只有第一个被匹配的值会被替换。例如：`x-code:key1,key2,key3`，正则匹配值key替换为abc，替换后的结果为`x-code:abc1,key2,key3`。|

8.  单击**确定**。


**相关文档**  


[批量配置域名](/intl.zh-CN/新版API参考/域名管理类接口/批量配置域名.md)

