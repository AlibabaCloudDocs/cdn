# EdgeRoutine场景和代码示例

本文为您介绍阿里云边缘Serverless产品—EdgeRoutine的简单场景示例和测试说明。Edgeroutine满足您在阿里云边缘节点运行代码的需求，提供轻量级可编程环境，利用阿里云CDN的2500+全球边缘节点，实现自动部署、就近接入的可编程CDN和Serverless服务。

## CLI环境准备

本地环境准备请参见[EdgeRoutine CLI工具使用说明](/cn.zh-CN/边缘程序/EdgeRoutine CLI工具使用说明.md)。

## 事件说明

您需要调用addEventListener函数去注册一个事件回调，目前支持fetch事件，fetch事件是由阿里云CDN的HTTP请求触发，即每次客户端访问CDN域名，将由CDN完成边缘就近接入，在边缘节点自动关联边缘Serverless服务，可以耦合到您的CDN业务生命周期（拦截或旁路），满足您的CDN可编程的需求，也可独立作为Serverless代替源站服务。

在fetch事件回调函数中，您必须使用event.respondWith去注册一个异步函数，该异步函数将返回一个Promise对象，Promise在JavaScript中是ES6异步的核心，可以理解为在将来这个对象会被解析成真正的响应内容返回给CDN甚至客户端。几乎所有的程序的addEventListener都是如此调用。

示例如下：

```
async function handleRespond(event) {
  return fetch("http://www.example.com");
}

addEventListener('fetch', (event) => {
  event.respondWith(handleRespond(event));
});
```

Edgeroutine支持Web标准API - Service Worker API，兼容标准ES6语法，且大量的Node.js第三方库直接使用，也支持标准的JS开发模型，为了满足您的测试需求，我们整理了相关的若干示例，您可以直接测试。

我们提供edge.ialicdn.com域名用来测试已默认配置的JavaScript Demo，示例源码见文章末尾。

-   示例代码使用js构建不同代码片段用于解决各种常见场景，目前是15+场景供您参考和学习。
-   为区分不同场景的示例，须在请求的body中携带json格式的kv对来将请求路由到不同的函数。

## Hello World

需求：该示例场景实现一个简单的边缘Serverless服务，无需回源，直接在边缘节点生成内容。

命令：

```
curl -v 'http://edge.ialicdn.com/a/b?x=y' -d '{"name": "helloworld"}'
```

![hello world](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/9811117951/p102006.gif)

## Geo

需求：该示例场景实现一个简单的边缘打点服务，可以采集到边缘节点的请求相关信息：如IP、地理、设备信息等。

命令：

```
curl -v 'http://edge.ialicdn.com/a/b?x=y' -d '{"name": "geo"}' -H "User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_4) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3770.80 Safari/537.36"
```

![Geo](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/9811117951/p102007.gif)

## Fetch

需求：该示例场景实现一个简单的边缘代理服务，在JS代码中调用内置api fetch做了http自请求，响应给客户端fetch的最终内容。

命令：

```
curl -v 'http://edge.ialicdn.com/a/b?x=y' -d '{"name": "fetch", "url": "http://a.hongxiaolong.com/xx"}'
```

![fetch](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/9811117951/p102008.gif)

## Request

需求：该示例场景实现一个简单的请求添加回源头功能。

命令：

```
curl -v 'http://edge.ialicdn.com/?x=y' -d '{"name":"request", "headers":{"aa":"bb"}, "body":"Hello ER!"}'
```

![request](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/9811117951/p102009.gif)

## Response

需求：该示例场景实现一个简单的添加回源响应头功能。

命令：

```
curl -v 'http://edge.ialicdn.com/?xx=yy' -d '{"name":"response", "headers":{"ra":"rb"}}'
```

![response](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/9811117951/p102010.gif)

## AB test

需求：该示例场景实现一个简单的AB测试的功能。

命令：

```
curl -v 'http://edge.ialicdn.com/?x=y' -d '{"name":"ab-test"}' -H "user-agent: a/canary-client/b"
```

![ab test](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/9811117951/p102011.gif)

## Multi origin

需求：该示例场景实现一个简单的边缘同拉多源合并功能，将不同源站的网页内容聚合后返回给客户端。

命令：

```
curl -v 'http://edge.ialicdn.com/?x=y' -d '{"name":"multi-origin"}'
```

![origin](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/0911117951/p102012.gif)

## Precache/Prefetch

需求：该示例场景实现一个简单的\(CDN\)预热功能，预热任务在响应客户端时将异步完成（需下个版本支持，目前忽略\)。

命令：

```
curl -v 'http://edge.ialicdn.com/' -d '{"name": "prefetch", "prefetch": ["http://a.hongxiaolong.com/prefetch", "http://b.hongxiaolong.com/prefetch"]}'
```

![Precache/Prefetch •](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/0911117951/p102013.gif)

![Precache/Prefetch •1](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/1911117951/p102014.gif)

## Race

需求：该示例场景实现一个简单的回源同拉功能，将回源速度最快的源站的内容优先返回给客户端。

命令：

```
curl -v 'http://edge.ialicdn.com/?x=y' -d '{"name":"race", "fetchList" : [ "https://www.taobao.com", "https://www.tmall.com", "https://www.baidu.com" ]}'
```

![race](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/1911117951/p102016.gif)

## ESI

需求：该示例场景实现一个简单的ESI服务。

命令：

```
curl -v 'http://edge.ialicdn.com/' -d '{"name":"esi","esi" : "<esi:include src=@http://www.baidu.com@> This is after the ESI for www.baidu.com"}'
```

![esi](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/1911117951/p102017.gif)

## Log

需求：该示例场景实现一个简单的边缘日志服务，在响应结束后异步地生成日志并回传给您的Server。

命令：

```
curl -v 'http://edge.ialicdn.com/' -d '{"name":"log"}'
```

![log](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/2911117951/p102018.gif)

## 3xx

需求：该示例场景实现一个简单的回源302跟随功能。

命令：

```
curl -v 'http://edge.ialicdn.com/' -d '{"name":"3xx"}'
```

![3xx](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/2911117951/p102020.gif)

## Redirect

需求：该示例场景实现一个简单的边缘请求重定向功能。

命令：

```
curl -v 'http://edge.ialicdn.com/a/b?x=y' -d '{"name": "redirect"}'
```

![redirect](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/2911117951/p102021.gif)

## Deny bot

需求：该示例场景实现一个简单的边缘反爬虫服务。

命令：

```
curl -v 'http://edge.ialicdn.com' -d '{"name":"deny-bot"}' -H "user-agent: xxxspider"
```

![deny bot](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/2911117951/p102022.gif)

## Waf

需求：该示例场景实现一个简单的边缘waf服务，当满足某些条件时，将禁止该请求。

命令：

```
curl -v 'http://edge.ialicdn.com' -d '{"name":"waf", "city":"Hangzhou"}'
```

![waf](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/2911117951/p102023.gif)

## 示例源码

```
addEventListener("fetch", function(event) {
  event.respondWith(_handleRouter(event));
});
async function _handleRouter(event) {
  let json = await event.request.json();
  if (json) {
    let name = json.name
      switch(name) {
        case "helloworld":
          return _handleHelloWorld(event);
        case "geo":
          return _handleGeo(event);
        case "fetch":
          return _handleFetch(event, json);
        case "request":
          return _handleRequest(event, json);
        case "response":
          return _handleResponse(event, json);
        // Cases
        case "ab-test":
          return _handleABTest(event, json);
        case "multi-origin":
          return _handleMultipleOriginConcate(event, json);
        case "prefetch":
          return _handlePrefetch(event, json);
        case "race":
          return _handleRace(event, json);
        case "esi":
          return _handleESI(event, json);
      case "log":
          return _handleEdgeLog(event, json);
        case "3xx":
          return _handleRedirect3XX(event, json);
        case "redirect":
          return _handleRedirectGeneral(event, json);
        case "deny-bot":
          return _handleDenyBot(event, json);
        case "waf":
          return _handleWAF(event, json);
        default:
          break;
      }
  }
  return new Response(
    `{ error : "invalid request" }`,
    {
      "status" : 403 ,
       "statusText" : "Forbidden"
    });
}
async function _handleHelloWorld(event) {
  return new Response("Hello World!");
}
async function _handleGeo(event) {
  const info = event.info;
  let remote_addr = info.remote_addr;
  let ip_isp_en = info.ip_isp_en;
  let ip_city_en = info.ip_city_en;
  let ip_region_en = info.ip_region_en;
  let ip_country_en = info.ip_country_en;
  let scheme = info.scheme;
  let detector_device = info.detector_device;
  let content = `Geo: ${remote_addr}, \
                      ${ip_isp_en},   \
                      ${ip_country_en},   \
                      ${ip_city_en},  \
                      ${ip_region_en},\
                      ${scheme},      \
                      ${detector_device}`;
  return new Response(content);
}
async function _handleFetch(event, json) {
  let fetchURL = json.url;
  if (fetchURL) {
    return await fetch(fetchURL);
  }
  return fetch("http://default.ialicdn.com");
}
async function _handleRequest(event, json) {
  let headers = json.headers;
  let body = json.body;
  const fetchInit = {
    body : body,
    headers: headers
  };
  return fetch("http://default.ialicdn.com", fetchInit);
}
async function _handleResponse(event, json) {
  let resp = await fetch("http://default.ialicdn.com");
  let headers = json.headers;
  for (var k in headers) {
    resp.headers.set(k, headers[k]);
  }
  return resp;
}
/** ================*
 * (1) DevOps       |
 * =================*/
function _shouldDoABTest(request) {
  // (1) if request's user agent match a certain string
  {
    const ua = request.headers.get("user-agent");
    if (ua && ua.match(/canary-client/)) {
      return true;
    }
  }
  // (2) whether we have special header
  {
    return request.headers.has("x-ab-test");
  }
}
async function _handleABTest(event, json) {
  const fetchInit = {
    method : event.request.method,
    headers: event.request.headers,
    body : "empty"
  };
  if (_shouldDoABTest(event.request)) {
    return fetch("http://default.ialicdn.com/dev", fetchInit);
  } else {
    return fetch("http://default.ialicdn.com", fetchInit);
  }
}
/** ==================================*
 * (2) Multiple Origin Concatenation  |
 ** ==================================*/
async function _handleMultipleOriginConcate(event, json) {
  const respInit = {
    headers: event.request.headers,
    body : json.body
  };
  // (1) We try to concate www.baidu.com and www.tmall.com together
  let {readable, writable} = new TransformStream();
  async function controller() {
    let r1 = await fetch("http://www.baidu.com");
    let r2 = await fetch("https://www.tmall.com");
    await r1.body.pipeTo(writable, {preventClose: true});
    await r2.body.pipeTo(writable);
  }
  controller();
  return new Response(readable, respInit);
}
/** ==================================*
 * (3) Precache/Prefetch               |
 ** ==================================*/
async function _fetchAndIgnore(url) {
  try {
    // Specify cdnProxy flag to make sure the request goes through the CDN
    let resp = await fetch(url);//, {cdnProxy: true});
    // Make sure to ignore the content otherwise the cache may not be valid
    await resp.ignore();
  } catch (e) {
    console.error("invalid URL: %s", url);
  }
}
async function _doPrefetchURLAsync(prefetchURL, event) {
  for (const url of prefetchURL) {
    event.waitUntil(_fetchAndIgnore(url));
  }
}
async function _handlePrefetch(event, json) {
  {
    const prefetchURL = json.prefetch;
    if (prefetchURL) {
      // Do not await it and let it run in background
      _doPrefetchURLAsync(prefetchURL, event);
      return new Response("Done Prefetch");
    }
  }
  return new Response("Miss Prefetch");
}
/** ==================================*
 * (4) Race
 ** ==================================*/
async function _handleRace(event, json) {
  let fetchList = json.fetchList;
  if (fetchList) {
    return Promise.race(fetchList.map((x) => fetch(x)));
  } else {
    return "forget to include fetchList field in your JSON";
  }
}
/** ==================================*
 * (5) Simple ESI
 ** ==================================*/
async function _handleESI(request, json) {
  let { readable, writable } = new TransformStream();
  let newResponse = new Response(readable);
  if (!json.esi) {
    return "forget to include template field in your JSON";
  }
  streamTransformBody(new BufferStream(json.esi), writable);
  return newResponse;
}
async function handleTemplate(encoder, templateKey) {
  const linkRegex = new RegExp("esi:include.*src=@(.*)@.*", 'gm');
  let result = linkRegex.exec(templateKey);
  let esi = "unknown";
  if (!result) {
    return encoder.encode(`<${templateKey}>`);
  }
  if (result[1]) {
    esi = await subRequests(result[1]);
  }
  return encoder.encode(`${esi}`);
}
async function subRequests(target){
  const init = {method: 'GET'};
  let response = await fetch(target, init);
  let text = await response.text();
  return text;
}
async function streamTransformBody(readable, writable) {
  const startTag = "<".charCodeAt(0);
  const endTag = ">".charCodeAt(0);
  let reader = readable.getReader();
  let writer = writable.getWriter();
  let templateChunks = null;
  while (true) {
    let { done, value } = await reader.read();
    if (done) break;
    while (value.byteLength > 0) {
      if (templateChunks) {
        let end = value.indexOf(endTag);
        if (end === -1) {
          templateChunks.push(value);
          break;
        } else {
          templateChunks.push(value.subarray(0, end));
          await writer.write(await translate(templateChunks));
          templateChunks = null;
          value = value.subarray(end + 1);
        }
      }
      let start = value.indexOf(startTag);
      if (start === -1) {
        await writer.write(value);
        break;
      } else {
        await writer.write(value.subarray(0, start));
        value = value.subarray(start + 1);
        templateChunks = [];
      }
    }
  }
  await writer.close();
}
async function translate(chunks) {
  const decoder = new TextDecoder();
  let templateKey = chunks.reduce(
    (accumulator, chunk) =>
    accumulator + decoder.decode(chunk, { stream: true }), "");
  templateKey += decoder.decode();
  return handleTemplate(new TextEncoder(), templateKey);
}
/** ==================================*
 * (6) Edge side conditional log
 ** ==================================*/
async function _doEdgeLog(data, writer) {
  let resp = await fetch("http://default.ialicdn.com/log",
    {
      method : "POST",
      body   : data,
      headers: [["content-type", "application/json"]]
    });
  console.log("logged");
  {
    let stream = new BufferStream("++++++++++++++++++++++++++++++\n");
    await stream.pipeTo(writer, {preventClose: true});
  }
  await resp.body.pipeTo(writer);
}
async function _handleEdgeLog(event, json) {
  let start= Date.now();
  let resp = await fetch("http://default.ialicdn.com", {
    method : event.request.method,
    headers: event.request.headers,
    body : json.body
  });
  // Get a promise that is fired when we send out everything
  let {readable, writable} = new TransformStream();
  // (1) first let the fetch request's response goes back and then we post
  //     the log back as well internally
  let endPromise = resp.body.pipeTo(writable, {preventClose: true});
  // (2) wait for endPromise to be fired to make sure that the body has been
  //     piped back to the client, and then we do the log
  event.waitUntil(endPromise.then(
    (v) => {
      let end = Date.now();
      let diff= (end - start);
      try {
        // You have to await your async promise since wait until is not
        // usable currently maybe. User can use wait until only before
        // returning the main request for now
        event.waitUntil(_doEdgeLog(`{ "cost(millisecond)" : ${diff} }`, writable));
      } catch (e) {
        console.error(`${e}`);
      }
    },
    (v) => {
      writable.abort();
      console.error("failed");
    }));
  console.error("XXXX");
  // return the response back
  return new Response(readable, {
    status: resp.status,
    headers: resp.headers
  });
}
/** ==================================*
 * (7) redirect-3xx
 ** ==================================*/
async function _handleRedirect3XX(event, json) {
  return fetch("http://www.taobao.com", {redirect: "follow"});
}
/** ==================================*
 * (8) redirect
 *   (1) UserAgent
 *   (2) Geo information
 ** ==================================*/
async function _handleRedirectGeneral(event, json) {
  const fetchInit = {
    method : event.request.method,
    body : json.body,
    headers : event.request.headers
  };
  {
    const ua = event.request.headers.get("user-agent");
    if (ua && ua.match(/firefox/i)) {
      return fetch("http://default.ialicdn.com/firefox", fetchInit);
    }
    if (ua && ua.match(/safari/i)) {
      return fetch("http://default.ialicdn.com/safari", fetchInit);
    }
  }
  {
    if (event.info.detect_device && event.info.detect_device.match(/iphone/)) {
      return fetch("http://default.ialicdn.com/iphone", fetchInit);
    }
  }
  return new Response("unknown request", {status: 403});
}
/** ==================================*
 * (9) Deny bot
 ** ==================================*/
async function _handleDenyBot(event, json) {
  {
    const ua = event.request.headers.get("user-agent");
    if (ua && ua.match(new RegExp("xxxspider", "i"))) {
      return new Response("Forbidden", {status: 403});
    }
  }
  return fetch("http://default.ialicdn.com");
}
/** ==================================*
 * (10) Simple WAF
 ** ==================================*/
async function _handleWAF(event, json) {
  let city = json.city;
  if (event.info.ip_city_en === city) {
    return new Response("Forbidden", {status: 403});
  }
  // back to origin
  return (JSON.stringify(event.info));
}
```

