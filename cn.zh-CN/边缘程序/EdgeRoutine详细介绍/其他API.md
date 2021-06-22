# 其他API

本文为您介绍边缘程序ER（EdgeRoutine）中支持使用的其他API。

## URL对象

URL对象的定义，请参见MDN官方文档[URL](https://developer.mozilla.org/zh-CN/docs/Web/API/URL)。

## URLSearchParams

URLSearchParams的定义，请参见MDN官方文档[URLSearchParams](https://developer.mozilla.org/zh-CN/docs/Web/API/URLSearchParams)。

## TextDecoder

TextDecoder的定义，请参见MDN官方文档[TextDecoder](https://developer.mozilla.org/en-US/docs/Web/API/TextDecoder)。

## TextEncoder

TextEncoder的定义，请参见MDN官方文档[TextEncoder](https://developer.mozilla.org/en-US/docs/Web/API/TextEncoder)。

## Atob

Atob的详细定义，请参见MDN官方文档[WindowOrWorkerGlobalScope.atob\(\)](https://developer.mozilla.org/zh-CN/docs/Web/API/WindowBase64/atob)。

## BtoA

BtoA的详细定义，请参见MDN官方文档[WindowOrWorkerGlobalScope.btoa\(\)](https://developer.mozilla.org/zh-CN/docs/Web/API/WindowBase64/btoa)。

## setTimeout/clearTimeout/setInterval/clearInterval

setTimeout/clearTimeout/setInterval/clearInterval的定义，请参见MDN官方文档[window.setTimeout](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/setTimeout)。

**说明：**

-   setTimeout和setInterval的时间精度为毫秒级别，为了避免SideChannel攻击，真实精度建议设置为50毫秒。
-   每个请求都有实时间约束，如果当前设置的时间大于实时间会触发异常。例如实时间约束是60秒，设置到setTimeouts和setInterval的时间为100秒将会触发异常。
-   setTimeout和setInterval有资源限制，每次请求最多可以设置16次，如果设置了资源限制，clear后也不会递减上限，且setInterval每次触发都算一次，最多会触发16次。
-   以上回调函数均为请求边界的回调函数，如果取消或终止了设置该触发的请求，setTimeout和setInterval将不会被触发。

## setImmediate/clearImmediate

setImmediate/clearImmediate的定义，请参见MDN官方文档[window.setImmediate](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/setImmediate)。

setImmdediate会保证一次上下文切换，同时setImmediate有资源上限，每次请求最多触发16次，即您可以设置16次，即使清除了这16次上限还在。

## 字符串相关

-   `utf8ToString`：将UTF-8转换成字符串。
-   `utf16ToString`：将UTF-16转换成字符串。

以上函数对输入的缓冲区大小有固定限制，如果有大的数据转换使用`TextEcnoder/Decoder`，输入缓冲区不能大于1MB，如果大于1MB，您可以在JS中切割内容。

## Console

目前console在实际运行中无意义，仅在调试环境中有效。调试环境中支持的参数如下：

-   info
-   log
-   error
-   warn
-   trace
-   assert

