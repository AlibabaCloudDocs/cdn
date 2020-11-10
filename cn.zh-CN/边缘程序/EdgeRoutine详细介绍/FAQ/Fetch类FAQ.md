# Fetch类FAQ

本文为您列出了边缘程序ER（EdgeRoutine）的Fetch相关的常见问题。

## Fetch支持解压缩吗？

Fetch默认会自动解压缩，有以下三种解压缩行为：

-   decompress：默认行为，读取response的content-encoding头，从右往左数，第一个非Identity的值作为解压缩算法，例如`content-encoding: gzip, identity`，选择gzip当作算法。如果您删除了该算法参数，删除后的头如下：

    -   `content-encoding：identity, gzip`表示Fetch后返回的原始头，`content-encoding: identity`表示被ER删除后的头。
    -   `content-encoding: gzip`表示Fetch后返回的原始头，`content-encoding`表示被ER删除后的头。
    **说明：** 删除头后内容会透明显示，就像源站没有回gzip的内容。如果ER无法识别对应的算法会抛出异常，目前仅支持gzip算法，未来可能会支持brotli算法。

-   fallbackIdentity：与decompress相似，无法解压缩时不会报错，直接当作identity处理。这个异常是有意为之，因为内容是压缩过的，你的读取可能没意义，因为你可能需要处理。
-   manual：不解压缩。

您可以通过以下方式手动设置Fetch的解压缩策略：

-   `fetch(url, {decompress: "manual"})`
-   `fetch(url, {decompress: "fallbackIdentity"})`

## Fetch的最大限制是多少？

所有的上下文即浏览器请求的边缘截获，发起的子请求默认最大限制是32个，每一次3xx跟随也算32个，将来支持的cache API也算32个，如果您需要提高限制配额，请[提交工单](https://selfservice.console.aliyun.com/ticket/createIndex)申请。

## ER可以识别非法URL吗？

ER无法识别非法的URL，如果您的URL含有非法字符，会提示没有正确的encode，请您确保URL正确。

## 连接池的最大限制是多少？

ER会自动为Fetch做连接池功能，用以规避TCP或SSL的握手消耗。连接池的数量限制默认是128，超过128个连接后，连接池将不再进行cache连接，您可以申请提升配置，增加连接池的上限。

连接池属于用户级别的连接池，非请求级别。如果当前的连接池为空，ER会尝试新建连接。当您完整读取了某次请求的回复body时，ER才能cache连接。

以下代码可以确保将Fetch的body读取完毕。

```
async function fetchAndIgnore(url, options) {
  let response = await fetch(url, options);
  // 该方法调用可以使ER强制忽略回复的body，并保证body被读取完毕。
  await response.ignore();
}
```

