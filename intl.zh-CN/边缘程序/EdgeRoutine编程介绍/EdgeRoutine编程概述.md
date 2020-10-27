# EdgeRoutine编程概述

边缘程序ER（EdgeRoutine）是阿里云CDN推出的边缘Serverless计算环境，支持在CDN边缘节点执行您自行编写的JavaScript代码。

## EdgeRoutine编程简介

ER为您提供了轻量级可编程环境，满足您在阿里云CDN边缘节点运行JavaScript代码的需求。同时ER实现了Service Worker API的FetchEvent，且支持大部分Stream API，另外JavaScript本身自带了大量的API可以供您直接使用，例如Date、String等。

## 基本概念

ER编程涉及以下基本概念：

-   初始化上下文

    每个ER程序被加载时都会自动初始化上下文，该上下文是ER脚本在全局区域的变量或函数的上下文。上下文内部除了JavaScript定义的标准函数外，其他大部分Service Worker API均无法使用，支持使用的Service Worker API有`addEventListener`、`atob`和`btoa`。

    **说明：** 每个脚本都可以使用全局变量存储一些基本的JavaScript类型，例如string、number等。

    每个ER程序都有唯一一次初始化上下文的机会，即当ER程序被冷启动或程序代码内容被更新时，会执行ER全局区域的代码，且只会执行一次。由于CDN节点天然的全局分布式特征，在不同的节点您可能有多个不同的独立JavaScript虚拟机，在每个虚拟机上全局代码均会被执行一次。您初始化区域代码的CPU时间为50ms，即您可以用50ms的CPU时间去初始化自己的ER脚本。

    **说明：** 建议不要在ER脚本的全局区域储存过多数据，因为这些数据将包含在可用内存之内，会影响JavaScript引擎的GC垃圾回收机制。

-   注册事件回调函数

    您必须在ER的全局代码区域调用`addEventListener`注册事件回调函数，例如Fetch事件，用于拦截访问CDN的请求。对于Fetch事件，您必须调用`event.respondWith`去注册一个异步函数，该异步函数将返回一个Promise对象，即Promise必须被resolve成一个Response对象，用于返回给客户端发送的请求，否则视为ER程序错误。

-   回调函数调用机制

    您调用`addEventListener`注册的回调函数会在每次客户端发起请求时被调用，由于ER运行时的特性，多个回调函数可能会被同时调用，用于处理同时被拦截的多个客户端请求。

-   请求上下文

    当您注册的某个事件回调函数被调用时，ER程序将处于请求上下文状态。每个请求都会独立呼叫一次您注册的回调函数，可能同时有无数次回调函数被调用。由于回调函数可能被异步IO事件中断，您的JS执行沙箱可能同时有多个回调函数正在执行，因为每次执行的回调函数会共用同一个JS虚拟机，所以JS的全局对象对所有同时被执行的回调函数可见。所有的Service Worker API对象均是请求上下文绑定状态，如果您想访问非该请求上下文的Service Worker对象，将会触发JS异常，具体见以下示例。

    ```
    let invalidRequest = null;
    
    addEventListener('fetch', (event) => {
      event.respondWith(handle(event));
    });
    
    async function handle(event) {
      if (invalidRequest) {
        // 引用invalidRequest将会触发异常，因为该Request对象并非这次回调函数所触发。
        // 请求上下文
        console.log("UA: %s", invalidRequest.headers.get("user-agent"));
      } else {
        invalidRequest = event.request;
      }
    }
    ```

    以上示例中假设同时出现两次请求，某个域名下的Fetch回调函数`handle`将会被调用两次，第一次调用的全局变量`invalidRequest`为空，所以将第一次回调触发的`request`对象设置到全局对象中。第二次触发时试图引用该对象的属性`header`，此时会造成ER运行时异常，因为第二次触发时的请求上下文和第一次触发时的请求上下文不一样。如果您试图共享数据到不同请求的上下文中，请使用原生JS类型，例如string、arrayBuffer等，这些对象支持跨请求上下文存在。


