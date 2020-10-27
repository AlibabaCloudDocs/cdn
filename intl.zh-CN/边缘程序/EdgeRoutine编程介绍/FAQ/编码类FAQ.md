# 编码类FAQ

本文为您列出了边缘程序ER（EdgeRoutine）编码相关的常见问题。

## ER支持哪些编码方式？

ER只支持UTF-8编码。

## ER是否影响透传？

不影响透传。透传是指不读取请求的body，而是以流的方式传递，即只更改头，body原封不动的传递出去。由于ER是纯网络流的透出，不会进入JS虚拟机。

**说明：** Fetch默认会解压缩，所以ER也会对流解压缩，如果您想原封不动的透出，请将decompress设置为manual。

## JavaScript的字符串是UTF-16标准编码吗？

不是。UTF-16编码格式不兼容ASCII编码，且存在Surrogate的codepoint。如果您的网页中存在使用Surrogate编码的codepoint，在有些情况下会导致字符错误。

`String.substring`是substring的UTF-16 codepoint，surrogate占2个UTF-16 codepoint，substring有可能把一个surrogate切成两个。如果substring中带有残缺的surrogate，会导致UTF-8将其编码为`INVALID REPLACEMENT CHAR （65533）`，该码在浏览器中会被跳过，不进行显示。

## 如果需要改动我的内容应该如何处理？

您可以使用以下代码进行缓冲。

```
text/arrayBuffer/JSON ...
```

**说明：**

-   进行流失处理时需注意surrogate的codepoint，确保surrogate不被切断，如果surrogate被切断，您将无法判断您读取的内容。如果您的大部分网页不包含需要使用surrogate的字符，仅有些emoji需要使用，则无特别注意事项。
-   阿里云即将推出HTML解析器，以帮助您更好地修改HTML代码内容，具体请关注阿里云官网信息。

## 如何将ArrayBuffer转换成UTF-8，或者将UTF-8转换成ArrayBuffer？

您可以使用TextEncoder和TextDecoder进行转换。

