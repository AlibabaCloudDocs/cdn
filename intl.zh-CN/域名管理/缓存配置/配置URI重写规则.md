---
keyword: [重写, 缓存]
---

# 配置URI重写规则

如果您访问的URI与源站URI不匹配，则需要将URI修改为与源站匹配的URI。您修改URI中的指定参数时，需要配置URI重写规则，规则匹配后会302重定向到目标URI。

## 适用场景

如果您需要将实际访问的URI修改为与源站匹配的URI，您可以通过配置重写功能，将实际访问的URI 302重定向到目标URI。例如，某些用户或客户端仍使用HTTP协议访问`www.example.com/hello`，您配置重写功能后，所有`www.example.com/hello`的请求都会重定向到`www.example.com/index.html`。

## 操作步骤

1.  登录[CDN控制台](https://cdn.console.aliyun.com)。

2.  在左侧导航栏，单击**域名管理**。

3.  在**域名管理**页面，单击目标域名对应的**管理**。

4.  在指定域名的左侧导航栏，单击**缓存配置**。

5.  单击**重写**页签。

6.  单击**添加**，根据您的实际需求，配置待重写URI、目标URI和执行规则。

    **说明：**

    -   单个域名最多可以配置50条重写规则。
    -   待重写URI和目标URI均支持正则表达式，但不支持大括号（`{ }`），配置含有大括号（`{ }`）的规则将不生效。
    ![重写](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/7227664161/p64171.png)

    |参数|说明|
    |--|--|
    |**待重写URI**|以正斜线（/）开头的URI，不含http://头及域名。支持PCRE正则表达式，例如：^/hello$。|
    |**目标URI**|以正斜线（/）开头的URI，不含http://头及域名，例如：/index.html。|
    |**执行规则**|支持**Redirect**和**Break**这两种规则。    -   **Redirect**：如果请求的URI匹配了当前规则，该请求将被302重定向到目标URI。
    -   **Break**：如果请求的URI匹配了当前规则，执行完当前规则后将不再匹配剩余规则。 |

7.  单击**确定**，完成配置。

    成功配置重写功能后，您可以在**重写**列表中，对当前的配置进行**修改**或**删除**操作。


## 配置示例

|示例|待重写URI|目标URI|执行规则|结果说明|
|--|------|-----|----|----|
|示例一|/hello|/index.html|Redirect|客户端请求`www.domain.com/hello`，CDN节点将返回302让客户端重新请求`www.domain.com/index.html`的内容。|
|示例二|^/$|/index.html|Redirect|客户端请求`www.domain.com`，CDN节点将返回302让客户端重新请求`www.domain.com/index.html`的内容。|
|示例三|/hello|/hello/index.html|Redirect|客户端请求`www.domain.com/hello`，CDN节点将返回302让客户端重新请求`www.domain.com/hello/index.html`的内容。|
|示例四|^/hello$|/index.html|Break|客户端请求`www.domain.com/hello`，CDN节点将返回`www.domain.com/index.html`的内容，且该请求不再继续匹配剩余规则。|

## 相关API

[BatchSetCdnDomainConfig](/intl.zh-CN/新版API参考/域名管理类接口/批量配置域名.md)

