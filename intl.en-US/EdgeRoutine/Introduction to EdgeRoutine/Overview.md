# Overview

EdgeRoutine \(ER\) is a lightweight and serverless computing environment that can run custom JavaScript code on Alibaba Cloud Content Delivery Network \(CDN\) nodes.

## What is ER?

ER is a lightweight and programmable environment that can run custom JavaScript code on Alibaba Cloud CDN nodes. ER supports the FetchEvent operation of the Service Worker API, most operations of the Stream API, and various JavaScript objects, such as Date and String.

## How it works

When you run JavaScript code in ER, the following processes are involved:

-   Initiate contexts

    When an ER program is loaded, the context is automatically initialized. The context belongs to the variables or functions in the ER script. You can use standard JavaScript functions and only certain Service Worker API operations such as `addEventListener`, `atob`, and `btoa` in the context. Other Service Worker API operations are not supported.

    **Note:** Each script can use global variables to store basic JavaScript objects such as String and Number.

    Each ER program has only one opportunity to initiate the context. When an ER program encounters a cold start or the program code is updated, the static initialization block of ER is run. The block is run only one time. CDN nodes are distributed. You can deploy different JavaScript virtual machines on different CDN nodes. The static initialization block is run on each virtual machine one time. If the CPU time for the initialization code is 50 milliseconds, you have 50 milliseconds of CPU time to initiate your ER script.

    **Note:** We recommend that you do not store a large amount of data in the static initialization block. Data stored in this block consumes memory resources and may affect the garbage collection \(GC\) mechanism of the JavaScript engine.

-   Register callback functions

    You must call `addEventListener` in the static initialization block of ER to register callback functions, such as fetch events, to fetch requests sent to Alibaba Cloud CDN. To register a fetch event, you must call `event.respondWith` to register an asynchronous callback function that returns a Promise object. The Promise object must be resolved into a Response object that is returned to the client request. Otherwise, ER throws exceptions.

-   Call callback functions

    The callback functions that you have registered by calling `addEventListener` are called each time a client request is sent to Alibaba Cloud CDN. ER allows multiple callback functions to be called at the same time to process client requests.

-   Request contexts

    When a callback function is called, the context of the ER program is invoked. Each request calls the callback functions one time. In some cases, the callback functions may be called frequently. A callback function may be interrupted by asynchronous I/O events. Multiple callback functions may be running in the JavaScript sandbox because the callback functions use the same JavaScript virtual machine. Therefore, the global JavaScript objects are visible to all running callback functions. All objects in Service Worker API operations are associated with the request contexts. If a request attempts to reference a Service Worker object that is not associated with the request, a JavaScript exception is thrown, as shown in the following example:

    ```
    let invalidRequest = null;
    
    addEventListener('fetch', (event) => {
      event.respondWith(handle(event));
    });
    
    async function handle(event) {
      if (invalidRequest) {
        // Referencing invalidRequest triggers an exception because the Request object is not invoked by this callback function.
        // The request context.
        console.log("UA: %s", invalidRequest.headers.get("user-agent"));
      } else {
        invalidRequest = event.request;
      }
    }
    ```

    In the preceding example, two requests are sent to Alibaba Cloud CDN. The `handle` function in the fetch request configured for the domain name is called two times. At the first time, the global variable `invalidRequest` is empty and the `Request` object is passed into the global object. At the second time, the request attempts to reference the `header` property of the object. ER throws an exception because the request context is different from the one invoked by the first request. If you need to share data among contexts of different requests, use native JavaScript objects such as String and ArrayBuffer that support contexts of different requests.


