# HTMLStream用法

本文为您介绍使用HTMLStream实时修改HTML页面流的方法。

## 背景介绍

在边缘程序ER（EdgeRoutine）的场景中前端场景占了很大一部分，由于边缘有不少特殊的请求数据，例如UA、地理信息和IP等，因此有不少需要在边缘实时更改HTML的需求。常规的更改方式是使用正则表达式制作adhoc的解析器更改，但使用该方法容易出错且不利用流式处理，使用开源JavaScript的解析器，例如parse5、htmlparser2等，对内存的消耗大、性能损失高。为了解决该问题，ER推出了边缘的HTML流式解析器，专门用于流式的修改HTML代码和页面。

**说明：** 该功能并非Web标准，属于ER内置的扩充功能。

## 举例说明

-   场景描述

    假设您需要将HTML页面中所有的`<a/>`标签修改后全部指向`http://www.taobao.com`，在ER中您可以使用以下代码实现。

-   代码示例

    ```
    addEventListener('fetch', (event) => {
      event.respondWith(handle(event));
    });
    
    async function handle(event) {
      // 1.假设exmaple页面返回的是待修改的HTML页面。
      const response = await fetch("http://www.example.com");
      // 2.您需要设置好HTML流式解析器。流式解析器允许您设置多个不同CSS Selector
      //    语法的捕获方式，然后注册回调函数进行改写。
      const htmlStream = new HTMLStream(
        response.body, // 放入需要改写的HTML流
        [[
          "a",         // 元素选择器，表示选择所有的`a`标签。
          {  
            // 注册回调函数对象，名为element的回调函数会在a标签（在DOM中为ElementNode）被调用。
            // 调用时您可以传入object来更改e的信息。
            element: function(e) {
              // 更改属性href
              e.setAttribute("href", "http://www.taobao.com");
            }
          }
        ]]);
      
      // 3.返回修改后的请求会浏览器。HTMLStream是个ReadableStream，所以任何能使用
      //    ReadableStream的地方均可使用HTMLStream。
      return new Response(htmlStream);
    }
                
    ```

-   结果分析

    以上代码便是简单的使用HTMLStream实时修改HTML页面流的方法，具体分析如下：

    -   通过Fetch您可以得到一个对请求回复的流的表示，实际ER可能没有从网络层读取body，该设计可以减少缓冲引起的大量GC问题。
    -   HTMLStream也是一个流，他的作用是TransformStream，即接受一个流，然后通过您注册的重写handler实时更改HTML页面。如果您要修改一个HTML页面，需要得到对应HTML的原始数据流，再把这个流当作输入，放入到新创建的HTML流中，例如上述代码示例中的示例2。
        -   HTMLStream的第一个参数是一个流，表示HTML原始数据。
        -   HTMLStream的第二个参数是个数组，表示一组重写器。重写器实际是一个数组，它包含一个选择器，用于选择需要改写的HTML及选择一个对象，对象中的部分property会被当作回调函数调用。例如上述例子中`["a" , {....}]`用于声明一个重写器，实际表示一个元素为2的数组。第一个字符串“a”表示元素选择器，在上述例子中表示找出文档中的所有a标签。第二个对象表示回调对象，对使用元素选择器而言，该对象可以包含以下三个函数：
            -   `element`函数，签名为function\(e\)，当元素选择器选择的element被解析时调用该函数。
            -   `comments`函数，签名为function\(e\)，当element中嵌套的注释被解析时调用该函数。
            -   `text`函数，签名为function\(e\)，当element中的文字被解析时调用该函数。该函数支持调用多次，因为流式处理的原因，HTMLStream可能只是正在处理一个字符串片段。
    -   HTMLStream是一个流，您可以直接回复这个流，但HTMLStream内部不会进行数据缓冲，且HTMLStream和常见的parse5、htmlparser2不同，HTMLStream不会生成DOM树，大大减少了处理时间和内存消耗，确保进行HTML解析的同时，保持高吞吐和并发。

