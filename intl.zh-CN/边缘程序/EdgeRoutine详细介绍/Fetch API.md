# Fetch API

本文为您介绍Fetch API的定义和相关参数信息。

## Fetch API方法定义

Fetch是完全异步的线程，只要您不使用await，Fetch就不会阻塞脚本执行，目前每次可以发起32个子请求，由于底层采用的是长连接，您无需担心性能，也不用主动处理连接池。

Fetch可以进行HTTP或HTTPS请求，每一次redirect都算一次请求，每一个Fetch最多可以支持12次redirect。

-   方法定义

    `fetch(arg, init)`，Fetch的详细定义请参见MDN官方文档[WorkerOrGlobalScope.fetch\(\)](https://developer.mozilla.org/zh-CN/docs/Web/API/WindowOrWorkerGlobalScope/fetch)。

-   方法限制

    -   目前Fetch API只支持域名，不支持IP地址，HTTP请求对应的端口为80，HTTPS请求对应的端口为443。
    -   init参数内部的credentials、referrer、 referrerPolicy、cache和integrity无任何意义。

        **说明：** 未来会支持cache参数，目前无意义。

    -   redirect默认值为manual，即不主动跟随3xx，如果需要跟随3xx，需将redirect设置为follow。
    **说明：**

    -   对浏览器内部的多种Fetch模式不做区分，例如`CROS fetch`，在CDN上您可以Fetch任何源站。
    -   如果需要修改以上限制，请[提交工单](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex)。

## Redirect

Fetch运行支持3xx跟随，即3xx重定向。3xx包含的status code有301、302、303、307和308。根据标准您可以指定以下三种行为，默认的行为是manual，即不主动跟随3xx。

-   `{redirect: "manual"}`：不跟随3xx，您自己处理。
-   `{redirect: "error"}`：3xx直接报错。
-   `{redirect: "follow"}`：跟随3xx，最多支持20次。

重定向方案见下表。

|状态码|重定向说明|
|---|-----|
|301、302、303、308|请求方法改成GET，body被忽略。|
|307|只跟随GET方法，其他方法会报错。|

**说明：** 重定向的地址来源于Location头，Location必须出现，否则会报错。

-   Location可以含有一个英文逗号（,）分割的URL表单，但只有第一个会被使用，其他均被忽略。
-   Location可以含有绝对URL或者相对URL。

## Decompress

Fetch允许您配置API的解压缩模式，例如`fetch("https://www.example.com"，{decompress: "manual"})`。Fetch的decompress参数有以下三种值：

-   manual：不解压缩。如果Fetch的服务器将压缩后的数据发送回来，则在ER中会读取到被压缩的数据。
-   decompress：自动解压缩。目前Fetch支持Gzip压缩模式，ER会根据content-encoding头自动侦测或者使用解压缩。ER如果执行了解压缩，会自动修改content-encoding的值，如果删除了其中的Gzip项，为了防止透传时出现错误，您可以进行如下设置：

    -   `content-encoding：gzip`表示可以被ER识别。
    -   `content-encoding：gzip, identity`表示可以被ER识别。
    **说明：** 其他非Gzip的算法，目前会报错。

-   fallbackIdentity：类似decompress，如果无法识别压缩，则默认不解压缩。

**说明：**

-   Fetch的默认解压缩值是decompress，即自动解压缩Gzip。
-   自动压缩后如果回复中有content-length头，该content-length头表示未被解压缩前的字符大小，此时不能随意透传content-length头，因为content-length的大小此时不再反应解压缩完成后的数据大小。

## CdnProxy

当您在ER内发起Fetch子请求时，默认由ER直接向公网发起HTTP请求（例如下图中的第5步），您也可以用cdnProxy通过CDN回源链路来代理请求（请求链路见下图中的7→8→9→10），cdnProxy的用法是`fetch("http://www.example.com", {cdnProxy: true})`，使用cdnProxy的好处在于Fetch的URL获得的数据将默认缓存在CDN中，后续的Fetch请求可直接命中缓存并返回给ER，无需真正地向源站重新拉取数据。

**说明：** 您通过cdnProxy发起Fetch的域名（例如示例中的www.example.com）必须是已经接入阿里云CDN的域名，否则会返回403，该方法会自动触发域名在CDN上的所有配置，包括缓存、回源等规则。

![原理](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/2099230161/p86758.png)

## content-length

如果您使用Fetch请求数据时设置了content-length，Fetch会采用content-length的编码，同时会改变Fetch发送body的默认行为。如果您不设置content-length，Fetch会主动把body流的所有数据读取出来并发送，发送使用chunk-encoding。

-   content-length设置
    -   content-length为非负数：根据您设置的值从发送的body流读取相应的字节后发送，发送采用content-length，如果content-length为0，则不发送任何数据。
    -   content-length为非法值：继续使用chunk-encoding发送所有body的值。
-   举例说明

    Fetch会自动解压缩内容，解压缩后response的content-length仍然存在，该content-length表示未被解压缩前的数据大小。如果您改动body后再使用Fetch需注意content-length，否则发送的内容可能会出错，具体见以下示例。

    ```
    addEventListener('fetch', (event) => {
      event.respondWith(h(event));
    });
    
    async function h(event) {
      return fetch("http://www.example.com", {
        headers: event.request.headers,
        method: event.request.method,
        body: "SomeData"
      });
    }
    ```

    上述示例中，假设客户端发送了一个POST请求，且header中包含了content-length。当您使用Fetch进行请求时，由于body复用了客户端request的header对象，会导致content-length的值和当前发送的body实际数据大小不一致。您透传header时一定要关注body的实际大小是否发生改变。


## Headers

-   定义

    Headers的定义，请参见MDN官方文档[Headers](https://developer.mozilla.org/zh-CN/docs/Web/API/Headers)。

-   限制

    header内部会记录内存消耗，header对象可以存储的最大header是8K。如果单个header对象超用，会触发JS exception。

-   黑名单

    header有黑名单，无法读写以下头，如果您读取会造成exception。

    -   expect
    -   te
    -   trailer
    -   upgrade
    -   proxy-connection
    -   connection
    -   keep-alive
    -   dnt
    -   host
    -   其他内部头

## Request

-   定义

    Request的定义，请参见MDN官方文档[Request](https://developer.mozilla.org/zh-CN/docs/Web/API/Request)。

-   限制

    Request对象的以下属性没有实现，在CDN上下文中没有意义。

    -   context
    -   credentials
    -   destination
    -   integrity
    -   mode
    -   referrer
    -   referrerPolicy
    -   cache：目前没有实现，将来有意义。
-   常见使用

    -   获得请求方法：`request.method`。
    -   获得请求url：`request.url`。
    -   获得请求头：`request.headers`。
    -   获得请求负载：`request.body`，body是一个ReadableStream对象。
    -   获得JSON：`await request.json()`。
    -   获得表单数据：`await request.formData()`。
    -   获得UTF8字符串：`await request.text()`。
    Request接口是标准的扩充，既可以忽略body，又确保body可以读完，且不会将内存读入JavaScript虚拟机，从而避免了GC造成的延时，确保请求流的body从底层的socket中全部读出。对于`await request.ignore()`，如果您不需要读取Fetch的body或者不感兴趣，建议所有的Fetch请求都调用`request.ignore`，可以有效提高性能，因为运行时会自动把读取完body的请求发送至连接池中供下次复用。


## Response

-   定义

    Response的定义，请参见MDN官方文档[Response](https://developer.mozilla.org/zh-CN/docs/Web/API/Response)。

-   限制

    Response对象的useFinalURLS和error属性没有实现，在CDN上下文中没有意义。

-   常见使用
    -   获得回复码：`response.status`。
    -   获得回复reason phrase：`response.statusText`。
    -   获得回复头：`response.headers`。
    -   获得回复URL：`response.url`，表示该回复是对应的URL发送的。
    -   获得所有redirect的URL list，属于非标准：`response.urlList`，类似Request对象实现了body mixin，使用类似方法您可以获得body对象。

## FormData

-   定义

    FormData的定义，请参见MDN官方文档[FormData](https://developer.mozilla.org/zh-CN/docs/Web/API/FormData)。

-   限制

    FormData类似Header，有内部大小限制，如果过大FormData会出现异常。如果把FormData当作HTTP body发送，默认的`content-type`是`form-data/multipart`。


## URLSearchParams

-   定义

    URLSearchParams的定义，请参见MDN官方文档[URLSearchParams\(\)](https://developer.mozilla.org/zh-CN/docs/Web/API/URLSearchParams/URLSearchParams)。

-   限制

    如果把URLSearchParams当作HTTPbody发送，默认的`content-type`是`application/x-www-form-urlencode`，最大限制为1000字节。


## Blob和File

-   定义
    -   File的定义，请参见MDN官方文档[File](https://developer.mozilla.org/zh-CN/docs/Web/API/File)。
    -   Blob的定义，请参见MDN官方文档[Blob](https://developer.mozilla.org/zh-CN/docs/Web/API/Blob)。
-   限制

    为了和标准保持一致，ER提供了Blob和File这两个类。由于ER不支持读写文件，为了满足标准，您可以使用这两个类，如果使用这两个类提供给回复的body，`content-type`是`Blob`和`File`设置的mime type，和标准一致。


