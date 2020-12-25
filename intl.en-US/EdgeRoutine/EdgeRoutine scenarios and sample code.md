# EdgeRoutine scenarios and sample code

This topic describes the scenarios that are supported by EdgeRoutine \(ER\) and test instructions. ER is a lightweight and serverless computing environment that can run custom JavaScript code on Alibaba Cloud Content Delivery Network \(CDN\) nodes. Provided with more than 2,500 CDN edge nodes deployed across the world, ER supports programmable Alibaba Cloud CDN and serverless services. These services can be automatically deployed and consumed on responsive CDN nodes that are closest to clients.

## Prepare the CLI environment

For more information, see [Work with EdgeRoutine CLI](/intl.en-US/EdgeRoutine/Work with EdgeRoutine CLI.md).

## Events

You can use the addEventListener method to register an event handler. Fetch events are supported. Fetch events are triggered by HTTP requests that are sent to Alibaba Cloud CDN. Each request that a client sends to an accelerated domain name is redirected to the responsive CDN node that is closest to the client. Fetch events are automatically associated with serverless services that are deployed on the CDN node. Requests are coupled with the lifecycle of Alibaba Cloud CDN and then blocked or redirected based on the lifecycle stage to which Alibaba Cloud CDN belongs. This allows you to program your Alibaba Cloud CDN service or use the Alibaba Cloud CDN service as a serverless origin server.

In the event handler, use the event.respondWith method to register a function that asynchronously executes operations. This function returns the Promise object. This object is a core feature of ECMAScript 6 \(ES6\) in the implementation of asynchronous programming. In later versions, the Promise object will be parsed into the actual response header and returned to Alibaba Cloud CDN or clients. Most programs call the addEventListener method in this way.

Sample code:

```
async function handleRespond(event) {
  return fetch("http://www.example.com");
}

addEventListener('fetch', (event) => {
  event.respondWith(handleRespond(event));
});
```

ER supports the Service Worker API, which is a web API. This API is compatible with ES6 syntax and can use third-party Node.js libraries. ES also supports standard JavaScript development models. This topic provides several code blocks that can be used in different scenarios.

edge.ialicdn.com is used in the following examples to test a preconfigured JavaScript demo. The sample source code is provided at the end of this topic.

-   The sample code uses JavaScript to build code snippets that can be used in a variety of scenarios. Alibaba Cloud CDN provides more than 15 sample scenarios.
-   To distinguish between different scenarios, the request body must carry a key-value pair in the JSON format. This way, requests are redirected to the required functions.

## Hello World

Requirements: This scenario shows how to build a simple serverless service on a CDN node where content can be generated. This way, Alibaba Cloud CDN does not need to redirect requests to an origin server.

Command:

```
curl -v 'http://edge.ialicdn.com/a/b?x=y' -d '{"name": "helloworld"}'
```

![hello world](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7244083061/p102006.gif)

## Geo

Requirements: This scenario shows how to build a simple service that enables event tracking on CDN nodes. Event tracking collects information about requests that are sent to CDN nodes, such as the IP address, geographic location, and device information.

Command:

```
curl -v 'http://edge.ialicdn.com/a/b?x=y' -d '{"name": "geo"}' -H "User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_4) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3770.80 Safari/537.36"
```

![Geo](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5720888061/p102007.gif)

## Fetch

Requirements: This scenario shows how to build a simple proxy on a CDN node. The built-in fetch API operation is called in the JavaScript code to create a custom request. The CDN node then returns the requested content to the client.

Command:

```
curl -v 'http://edge.ialicdn.com/a/b?x=y' -d '{"name": "fetch", "url": "http://a.hongxiaolong.com/xx"}'
```

![fetch](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7244083061/p102008.gif)

## Request

Requirements: This scenario shows how to add a header to a back-to-origin request.

Command:

```
curl -v 'http://edge.ialicdn.com/?x=y' -d '{"name":"request", "headers":{"aa":"bb"}, "body":"Hello ER!"}'
```

![request](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7244083061/p102009.gif)

## Response

Requirements: This scenario shows how to add a header to a back-to-origin response.

Command:

```
curl -v 'http://edge.ialicdn.com/?xx=yy' -d '{"name":"response", "headers":{"ra":"rb"}}'
```

![response](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7244083061/p102010.gif)

## AB test

Requirements: This scenario shows how to run a simple A/B test.

Command:

```
curl -v 'http://edge.ialicdn.com/?x=y' -d '{"name":"ab-test"}' -H "user-agent: a/canary-client/b"
```

![ab test](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7244083061/p102011.gif)

## Multi origin

Requirements: This scenario shows how to enable aggregation of content that is retrieved from different origin servers. This allows you to return aggregated content from different origin servers to clients.

Command:

```
curl -v 'http://edge.ialicdn.com/?x=y' -d '{"name":"multi-origin"}'
```

![origin](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7244083061/p102012.gif)

## Precache/Prefetch

Requirements: This scenario shows how to prefetch content from an origin server. Prefetch tasks are asynchronously performed when CDN nodes return responses to clients. This feature will be supported in later versions.

Command:

```
curl -v 'http://edge.ialicdn.com/' -d '{"name": "prefetch", "prefetch": ["http://a.hongxiaolong.com/prefetch", "http://b.hongxiaolong.com/prefetch"]}'
```

![Precache/Prefetch •](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7244083061/p102013.gif)

![Precache/Prefetch •1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8244083061/p102014.gif)

## Race

Requirements: This scenario shows how to retrieve content from multiple origin servers and return the content that is first retrieved to clients.

Command:

```
curl -v 'http://edge.ialicdn.com/?x=y' -d '{"name":"race", "fetchList" : [ "https://www.taobao.com", "https://www.tmall.com", "https://www.baidu.com" ]}'
```

![race](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8244083061/p102016.gif)

## ESI

Requirements: This scenario shows how to assemble content by using Edge Side Includes \(ESI\).

Command:

```
curl -v 'http://edge.ialicdn.com/' -d '{"name":"esi","esi" : "<esi:include src=@http://www.baidu.com@> This is after the ESI for www.baidu.com"}'
```

![esi](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8244083061/p102017.gif)

## Log

Requirements: This scenario shows how to enable logging on a CDN node. After the CDN node returns a response to a client, relevant log data is asynchronously generated and delivered to your server.

Command:

```
curl -v 'http://edge.ialicdn.com/' -d '{"name":"log"}'
```

![log](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8244083061/p102018.gif)

## 3xx

Requirements: This scenario shows how to enable CDN nodes to redirect requests to the required addresses, retrieve the requested content, and then return the content to the clients after the CDN nodes receive the 302 status code from the origin servers.

Command:

```
curl -v 'http://edge.ialicdn.com/' -d '{"name":"3xx"}'
```

![3xx](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8244083061/p102020.gif)

## Redirect

Requirements: This scenario shows how to enable CDN nodes to redirect requests.

Command:

```
curl -v 'http://edge.ialicdn.com/a/b?x=y' -d '{"name": "redirect"}'
```

![redirect](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9244083061/p102021.gif)

## Deny bot

Requirements: This scenario shows how to deploy a simple anti-bot service on CDN nodes.

Command:

```
curl -v 'http://edge.ialicdn.com' -d '{"name":"deny-bot"}' -H "user-agent: xxxspider"
```

![deny bot](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9244083061/p102022.gif)

## Waf

Requirements: This scenario shows how to enable Web Application Firewall \(WAF\) for CDN nodes to block requests under specified conditions.

Command:

```
curl -v 'http://edge.ialicdn.com' -d '{"name":"waf", "city":"Hangzhou"}'
```

![waf](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9244083061/p102023.gif)

## Sample source code

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
  return new Response("Hello World!") ;
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
  event.request.headers.delete("content-length");
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
  if (! json.esi) {
    return "forget to include template field in your JSON";
  }
  streamTransformBody(new BufferStream(json.esi), writable);
  return newResponse;
}
async function handleTemplate(encoder, templateKey) {
  const linkRegex = new RegExp("esi:include.*src=@(. *)@.*", 'gm');
  let result = linkRegex.exec(templateKey);
  let esi = "unknown";
  if (! result) {
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

