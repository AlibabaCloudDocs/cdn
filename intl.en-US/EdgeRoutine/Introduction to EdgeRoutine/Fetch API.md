# Fetch API

This topic describes the Fetch API and its parameters.

## Definition of the Fetch methods

Fetch is an asynchronous thread. If you do not use the await keyword, Fetch does not block the execution of scripts. You can use Fetch to make 32 subrequests at a time. The underlying layer uses persistent connections. Therefore, the performance is stable and you do not need to manage connection pools.

You can call the Fetch API to make HTTP or HTTPS requests. Each redirect is counted as one request. Each Fetch API call supports a maximum of 12 redirects.

-   Method definition

    The Fetch method is `fetch(arg, init)`. For more information about the Fetch method, see [WorkerOrGlobalScope.fetch\(\)](https://developer.mozilla.org/zh-CN/docs/Web/API/WindowOrWorkerGlobalScope/fetch).

-   Method limits

    -   The Fetch API supports only domain names. IP addresses are not supported. HTTP requests use port 80 and HTTPS requests use port 443.
    -   The credentials, referrer, referrerPolicy, cache, and integrity parameters in the init object are not in use.

        **Note:** The cache parameter will be used in later versions.

    -   The redirect parameter is set to manual by default. This indicates that fetch requests do not follow 3xx redirects. If you want fetch requests to follow 3xx redirects, set the redirect parameter to follow.
    **Note:**

    -   Browsers treat fetch requests in different modes in the same way. For example, `CROS fetch` can be used to fetch resources from any origin servers through Alibaba Cloud Content Delivery Network \(CDN\).
    -   If you need to modify the preceding settings, [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex).

## Redirect

The Fetch API supports 3xx redirects. Fetch requests can follow 3xx redirects. HTTP 3xx status codes include 301, 302, 303, 307, and 308. The redirect parameter is set to manual by default, which indicates that fetch requests do not follow 3xx redirects. You can set the redirect parameter to the following values based on your business requirements:

-   `{redirect: "manual"}`: Fetch requests do not follow 3xx redirects. You must manually handle 3xx redirects.
-   `{redirect: "error"}`: Exceptions are thrown when a fetch request encounters a 3xx redirect.
-   `{redirect: "follow"}`: Fetch requests follow 3xx redirects. The maximum number of 3xx redirects supported by the Fetch API is 20.

The following table describes different 3xx redirects.

|Status code|Redirect description|
|-----------|--------------------|
|301, 302, 303, and 308|The request method is changed to GET and the body is ignored.|
|307|Requests follow 3xx redirects only if the request method is GET. Other request methods throw exceptions.|

**Note:** The URL to which a request is redirect is provided by the Location header. If the Location header is missing, an exception is thrown.

-   The Location header can contain a list of URLs separated with commas \(,\). However, requests are redirected to only the first URL in the list. Other URLs are ignored.
-   The Location header can contain absolute URLs or relative URLs.

## Decompress

The Fetch API allows you to configure a decompression mode, for example, `fetch("https://www.example.com",{decompress: "manual"})`. The decompress parameter supports the following values:

-   manual: does not decompress data. If the server returns compressed data to a fetch request, the data that ER receives is also compressed.
-   decompress: automatically decompresses data. The Fetch API supports Gzip compression. ER automatically detects or decompresses data based on the content-encoding header. After ER decompresses data, ER automatically modifies the value of content-encoding. If the Gzip parameter is deleted, you can configure the following settings to prevent exceptions when you pass data:

    -   `content-encoding: gzip`: The decompression algorithm can be recognized by ER.
    -   `content-encoding: gzip, identity`: The decompression algorithm can be recognized by ER.
    **Note:** Algorithms other than Gzip cause exceptions.

-   fallbackIdentity: This value is similar to the decompress value. If this value cannot be recognized by ER, ER does not decompress data.

**Note:**

-   The default value is decompress, which indicates that ER automatically uses Gzip to decompress data.
-   After the server compresses the data, you cannot pass the content-length header as needed if the response contains the content-length header. This is because the content-length header indicates the size of the data before decompression.

## CdnProxy

When you use the Fetch API to fetch data, you can use Alibaba Cloud CDN as a proxy to process requests. For example, you can set `fetch("http://www.example.com", {cdnProxy: true})`. The domain name from which you use the Fetch API to fetch resources must be added to Alibaba Cloud CDN. Otherwise, a 403 status code is returned. Using Alibaba Cloud CDN as a proxy automatically triggers all business logic of Alibaba Cloud CDN, including the caching and back-to-origin processes.

## content-length

If you configure the content-length header in a fetch request, data is encoded in the encoding scheme specified in the content-length header. The way how the Fetch API transmits data is also changed. If you do not configure the content-length header, the Fetch API automatically fetches all data in the body stream and transmits the data. The transmitted data is encoded by using the chunked transfer encoding scheme.

-   Configure content-length
    -   If the content-length header is set to a negative value: The Fetch API fetches data from the body stream based on the content-length header and transmits the fetched data. If content-length is set to 0, no data is transmitted.
    -   If the content-length header is set to an invalid value: The Fetch API transmits all values in the body. The transmitted data is encoded by using the chunked transfer encoding scheme.
-   Examples

    The Fetch API automatically decompresses data. After the data is decompressed, the content-length header is still retained in the response. The content-length header indicates the size of the response before it is decompressed. If you call the Fetch API after you modify the body, check whether you need to modify the content-length header. Otherwise, the content that is transmitted may be incorrect. For more information, see the following example:

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

    In the preceding example, a POST request that contains the content-length header is sent from a client. When you call the Fetch API to fetch data, the request body uses the Headers object from the client request. The value of the content-length header may be different from the actual size of the body. When you pass the Headers object, check whether the size of the body is changed.


## Headers

-   Definition

    For more information about the Headers object, see [Headers](https://developer.mozilla.org/zh-CN/docs/Web/API/Headers).

-   Limits

    A header records the amount of consumed memory resources. The object in the header can be at most 8 KB in size. If the size of a Headers object exceeds this limit, a JavaScript exception is thrown.

-   Blacklist

    ER provides a header blacklist. If you attempt to read and write headers in the blacklist, exceptions are thrown. You cannot read or write the following headers:

    -   expect
    -   te
    -   trailer
    -   upgrade
    -   proxy-connection
    -   connection
    -   keep-alive
    -   dnt
    -   host
    -   Reserved headers

## Request

-   Definition

    For more information about the Request operation, see [Request](https://developer.mozilla.org/zh-CN/docs/Web/API/Request).

-   Limits

    The following properties of the Request object are not in use in contexts. They do not take effect in contexts.

    -   context
    -   credentials
    -   destination
    -   integrity
    -   mode
    -   referrer
    -   referrerPolicy
    -   cache: not in use. It does not take effect in contexts. It will be used in later versions of ER.
-   Use cases of the Request operation

    -   Fetches the request method: `request.method`.
    -   Fetches the request URL: `request.url`.
    -   Fetches the request header: `request.header`.
    -   Fetches the request payload: `request.body`. The Body property \(body\) is a ReadableStream object.
    -   Fetches JSON data: `await request.json()`.
    -   Fetches form data: `await request.formData()`.
    -   Fetches strings encoded in UTF-8: `await request.text()`.
    The Request operation is a standard API operation. It can ignore the body while fetching all values of the body without consuming the memory resources of ER. This prevents long garbage collection \(GC\) time and fetches all values of the request body from the underlying sockets. If you do not need to fetch the body, you can call `request.ignore` in `await request.ignore()` for all fetch requests. After the body of a request is fetched, ER automatically sends the request to the connection pool for future use.


## Response

-   Definition

    For more information about the Response operation, see [Response](https://developer.mozilla.org/zh-CN/docs/Web/API/Response).

-   Limits

    The useFinalURLS and error properties of the Response object are not in use. They do not take effect in the contexts of requests redirected to CDN nodes.

-   Use cases of the Response operation
    -   Fetches the HTTP status code: `response.status`.
    -   Fetches the reason phrase of a response: `response.statusText`.
    -   Fetches the response header: `response.headers`.
    -   Fetches the response URL: `response.url`.
    -   Fetches a list of URLs that redirect to other URLs: `response.urlList`. It is a non-standard method. Similar to the implementation of the Body mixin by the Response object, you can use similar methods to fetch the Body object.

## FormData

-   Definition

    For more information about the FormData operation, see [FormData](https://developer.mozilla.org/zh-CN/docs/Web/API/FormData).

-   Limits

    The FormData operation is similar to the Headers operation. FormData limits the size of headers. If a header exceeds the upper limit, an exception is thrown. If you send FormData in the way of sending an HTTP request body, `content-type` is set to `form-data/multipart` by default.


## URLSearchParams

-   Definition

    For more information about the URLSearchParams operation, see [RLSearchParams\(\)](https://developer.mozilla.org/zh-CN/docs/Web/API/URLSearchParams/URLSearchParams).

-   Limits

    If you send URLSearchParams in the way of sending an HTTP request body, `content-type` is set to `application/x-www-form-urlencode` by default. The maximum data size is 1,000 bytes.


## Blob and File

-   Definition
    -   For more information about the File operation, see [File](https://developer.mozilla.org/zh-CN/docs/Web/API/File).
    -   For more information about the Blob operation, see [Blob](https://developer.mozilla.org/zh-CN/docs/Web/API/Blob).
-   Limits

    To meet the standards of the Blob and File operations, ER supports the Blob and File classes. ER does not support reading or writing files. You can pass the Blob and File classes supported by ER into the response body. The value of the `content-type` header is the same as that of the mime type parameter in the `Blob` or `File` operation.


