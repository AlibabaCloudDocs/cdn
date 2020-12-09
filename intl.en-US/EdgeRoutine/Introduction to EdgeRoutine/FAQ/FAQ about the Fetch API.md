# FAQ about the Fetch API

This topic provides answers to some commonly asked questions about the Fetch API supported by EdgeRoutine \(ER\).

## Does Fetch support decompression?

By default, automatic decompression is enabled for Fetch. Fetch supports the following decompression methods:

-   decompress: the default method. It reads the content-encoding header in the response and uses the decompression algorithm specified by the rightmost value, excluding Identity. For example, in `content-encoding: gzip, identity`, gzip is the decompression algorithm. If you delete this value from the response header, the following situations occur:

    -   `content-encoding: identity, gzip` is the fetched response header. `content-encoding: identity` is the response header after gzip is deleted.
    -   `content-encoding: gzip` is the fetched response header. `content-encoding` is the response header after gzip is deleted.
    **Note:** After the decompression algorithm is deleted from the response header, the data becomes visible. The same situation occurs if the origin server returns the data without using Gzip to compress the data. If ER cannot recognize the algorithm, ER throws an exception. ER supports only Gzip. Brotli may be supported in later versions.

-   fallbackIdentity: similar to decompress. ER does not throw exceptions if it fails to decompress data. Instead, it treats the algorithm value as the identity. In this case, no exceptions are thrown because the fetched data is compressed. You are unable to read the data without decompression.
-   manual: does not decompress data.

You can use the following methods to manually set a decompression policy for Fetch:

-   `fetch(url, {decompress: "manual"})`
-   `fetch(url, {decompress: "fallbackIdentity"})`

## What is the maximum number of subrequests supported by Fetch?

The maximum number of subrequests supported by Fetch is 32. This includes all contexts, which are equal to all requests captured on edge nodes. The maximum number of subrequests for 3xx redirects or Cache API calls is also 32. To request a quota increase, [submit ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex).

## Can ER recognize invalid URLs?

ER cannot recognize invalid URLs. If a URL contains invalid characters, ER prompts that the data is not correctly encoded. Make sure that your URL is valid.

## What is the maximum number of connections supported by a connection pool?

ER provides a connection pool to Fetch in case all connections are consumed by TCP or SSL handshakes. By default, a connection pool supports 128 connections. When the number of connections reaches 128, the connection pool stops caching connections. If you want to create more connections, request a quota increase.

A connection pool is created for each user instead of for each request. If no connection is established in the connection pool, ER attempts to create connections. ER caches a connection only after the entire response body is retrieved.

The following code ensures that the entire response body is retrieved after it is fetched:

```
async function fetchAndIgnore(url, options) {
  let response = await fetch(url, options);
  // This method forces ER to ignore the response body and ensures that the entire response body is retrieved.
  await response.ignore();
}
```

