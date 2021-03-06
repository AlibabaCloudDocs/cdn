# 改写回源URI

当您需要改写回源请求中的URI时，可以配置回源URI改写功能。通过本文您可以了解配置重写规则的操作步骤。

当您的回源请求URI与源站的URI不匹配时，需要将您的回源请求URI修改为与源站匹配的URI，您可以根据实际需要配置多条改写匹配规则。

1.  登录[CDN控制台](https://cdn.console.aliyun.com)。

2.  在左侧导航栏，单击**域名管理**。

3.  在**域名管理**页面，单击目标域名对应的**管理**。

4.  在指定域名的左侧导航栏，单击**回源配置**。

5.  单击**回源URI改写**页签。

6.  单击**添加**。

7.  根据您的需求，配置需要改写的URI、目标URI和执行规则。

    ![改写回源URI](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/9664788951/p83537.png)

    |参数|示例|说明|
    |--|--|--|
    |需要改写的URI|^/hello$|以正斜线（/）开头的URI，不含http://头及域名。支持PCRE正则表达式。|
    |目标URI|/hello/test|以正斜线（/）开头的URI，不含http://头及域名。|
    |执行规则|空|如果配置了多条规则，在匹配执行当前规则后，继续匹配后续规则。|
    |break|如果配置了多条规则，在匹配执行当前规则后，后续规则将不再匹配，并且只修改URI部分，不修改URL的参数。|
    |enhance break|如果配置了多条规则，在匹配执行当前规则后，后续规则将不再匹配，但是匹配和修改整个URL（包括URI+参数）。|

    **说明：**

    -   **回源URI改写**功能中的执行规则`break`虽然不修改URL的参数部分，但是并不影响**回源参数改写**功能对URL中参数的改写。
    -   **回源URI改写**功能在配置执行规则`enhance break`的情况下，对URL中参数的改写可能会与**回源参数改写**功能对URL中参数的改写相冲突，这两个功能同时配置的时候，需要注意避免配置冲突。
    -   **回源URI改写**功能在配置执行规则的情况下，对URL中参数的改写可能会与**域名管理** \> **性能优化**页签下的**保留参数**或**忽略参数**功能相冲突，这三个功能同时配置的时候，需要注意避免配置冲突。
8.  单击**确定**，使改写规则开始执行和生效。

    您也可以在**回源URI改写**页面的规则列表中，单击**修改**或**删除**，对当前配置的规则进行相应操作。

    **说明：**

    -   单个域名可以配置的**回源URI改写**规则数量上限是50个。
    -   规则改写按照规则列表从上到下顺序执行的，此顺序可能会影响您的改写结果。
    -   **回源URI改写**功能与**重写**功能的区别在于，**重写**功能的作用位置是在CDN边缘节点上面，会影响CDN内部链路，也会改写缓存key，而**回源URI改写**功能的作用位置是在CDN回源节点上面，不影响CDN内部链路，不改写缓存key。

样例一

|待改写URI|^/hello$|
|目标URI|/index.html|
|执行规则|空|
|结果说明|原始请求：`http://domain.com/hello`改写后的回源请求：`http://domain.com/index.html`

该请求将会继续匹配**回源URI改写**规则列表中其余的规则。 |

样例二

|待改写URI|^/hello.jpg$|
|目标URI|/image/hello.jpg|
|执行规则|break|
|结果说明|原始请求：`http://domain.com/hello.jpg`改写后的回源请求：`http://domain.com/image/hello.jpg`

该请求将不再继续匹配**回源URI改写**规则列表中其余的规则。 |

样例三

|待改写URI|^/hello.jpg?code=123$|
|目标URI|/image/hello.jpg?code=321|
|执行规则|enhance break|
|结果说明|原始请求：`http://domain.com/hello.jpg?code=123`改写后的回源请求：`http://domain.com/image/hello.jpg?code=321`

该请求将不再继续匹配**回源URI改写**规则列表中其余的规则。|

样例四

使用场景：在文件名是变量的情况下添加URI前缀。

例如：将包含/xxx的URI（xxx代表任意文件名称，例如：/hello.jpg、/hello.html等等）改写为/image/xxx，即对根目录下的任意文件的URI都插入路径/image。

|待改写URI|^\(.\*\)$**说明：** ^\(.\*\)$代表任意字符，\(\)代表的是一个分组，可以在目标URI中通过$1来调用分组的变量内容。 |
|目标URI|/image$1**说明：** $1表示正则表达式中第一对圆括号中的表达式匹配到的内容，$2是第二个小括号里面的内容，依此类推。 |
|执行规则|break|
|结果说明|-   原始请求：`http://domain.com/hello.jpg`

改写后的回源请求：`http://domain.com/image/hello.jpg`

-   原始请求：`http://domain.com/hello.html`

改写后的回源请求：`http://domain.com/image/hello.html`


该请求将不再继续匹配**回源URI改写**规则列表中其余的规则。|

样例五

使用场景：在文件名是变量的情况下添加URI前缀。

例如：将包含/live/xxx的URI（xxx代表任意文件名称，例如：/live/hello.jpg、/live/hello.html 等等）改写为/image/live/xxx，即对目录 /live 下的任意文件的URI都插入路径/image。

|待改写URI|^/live/\(.\*\)$|
|目标URI|/image/live/$1|
|执行规则|break|
|结果说明|-   原始请求：`http://domain.com/live/hello.jpg`

改写后的回源请求：`http://domain.com/image/live/hello.jpg`

-   原始请求：`http://domain.com/live/hello.html`

改写后的回源请求：`http://domain.com/image/live/hello.html`


该请求将不再继续匹配**回源URI改写**规则列表中其余的规则。|

**相关文档**  


[批量配置域名](/cn.zh-CN/新版API参考/域名管理类接口/批量配置域名.md)

