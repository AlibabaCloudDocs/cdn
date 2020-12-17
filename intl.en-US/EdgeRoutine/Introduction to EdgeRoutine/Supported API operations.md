# Supported API operations

This topic describes the API operations that are supported by EdgeRoutine \(ER\).

## URL

For more information about the URL operation, see [URL](https://developer.mozilla.org/zh-CN/docs/Web/API/URL).

## URLSearchParams

For more information about the URLSearchParams operation, see [URLSearchParams](https://developer.mozilla.org/zh-CN/docs/Web/API/URLSearchParams).

## TextDecoder

For more information about the TextDecoder operation, see [TextDecoder](https://developer.mozilla.org/en-US/docs/Web/API/TextDecoder).

## TextEncoder

For more information about the TextEncoder operation, see [TextEncoder](https://developer.mozilla.org/en-US/docs/Web/API/TextEncoder).

## Atob

For more information about the Atob operation, see [WindowOrWorkerGlobalScope.atob\(\)](https://developer.mozilla.org/zh-CN/docs/Web/API/WindowBase64/atob).

## BtoA

For more information about the BtoA operation, see [WindowOrWorkerGlobalScope.btoa\(\)](https://developer.mozilla.org/zh-CN/docs/Web/API/WindowBase64/btoa).

## setTimeout/clearTimeout/setInterval/clearInterval

For more information about the setTimeout, clearTimeout, setInterval, and clearInterval operations, see [window.setTimeout](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/setTimeout).

**Note:**

-   The setTimeout and setInterval operations allow you to set a time period in milliseconds. To protect data from side-channel attacks, we recommend that you set the time period to 50 milliseconds.
-   Each request has a specific response time. If the specified time period is longer than the response time, an exception is thrown. For example, if the response time is 60 seconds and setTimeouts and setInterval are set to 100 seconds, an exception is thrown.
-   setTimeout and setInterval can be configured at most 16 times for each request. After the upper limit is set, it remains effective even if you call the clear method to cancel the specified time period. Each time that setInterval is invoked consumes one quota. setInterval can be invoked at most 16 times.
-   The preceding callback functions apply to the boundary of a request. If the request for which setTimeout or setInterval is set is canceled or terminated, they are not invoked.

## setImmediate/clearImmediate

For more information about the setImmediate and clearImmediate operations, see [window.setImmediate](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/setImmediate).

setImmdediate switches from one context to another context. setImmdediate can be invoked at most 16 times for each request. After you set this upper limit, it remains effective even if you clear it.

## String-related operations

-   `utf8ToString`: coverts UTF-8-encoded data to strings.
-   `utf16ToString`: converts UTF-16-encoded data to strings.

The preceding functions limit the buffer size. If you need to convert data in a large size, we recommend that you use `TextEcnoder/Decoder`. The input buffer can be at most 1 MB. If the input buffer exceeds 1 MB, you can call a JavaScript method to split the content.

## Console

The console operation takes effect only in staging environments. The console operation supports the following parameters in staging environments:

-   info
-   log
-   error
-   warn
-   trace
-   assert

