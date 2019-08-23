# 服务管理FAQ {#concept_371744 .concept}

-   统计分析相关

    [CDN访问日志统计与CNZZ的统计结果存在差异的原因是什么？](#section_9cx_x6p_0wk)

-   日志管理相关
    -   [CDN查看响应日志，为什么有408状态码日志信息？](#section_4ut_ssu_g6r)
    -   [日志的304状态码是什么原因？](#section_ohl_cql_ilp)
    -   [如何分析CDN访问日志？](#section_fpd_8ri_7k7)
-   诊断工具相关

    [如何查询CDN节点的IP？](#section_9p1_r9f_r2g)


## CDN访问日志统计与CNZZ的统计结果存在差异的原因是什么？ {#section_9cx_x6p_0wk .section}

-   CNZZ的统计方式是在每个页面放置一段JS代码，当您访问这个页面，并且页面加载成功时，JS才会统计到。如果有的页面加载失败或有的页面没有放这段JS代码，则无法统计。另外，如果其它网站中引用该网站中的某个文件、某些图片，CNZZ也无法统计到。
-   CDN的统计方式是基于日志中的每一个访问请求进行统计，所以统计结果更全面。另外，在计算PV的时候，如果同一个页面中有多个iframe标签，CDN计算的是多个PV。

如问题还未解决，请[提交工单](https://selfservice.console.aliyun.com/ticket/createIndex)。

## CDN查看响应日志，为什么有408状态码日志信息？ {#section_4ut_ssu_g6r .section}

该日志是由CDN对源站的健康检查导致的，是CDN的上层节点对源站发起了TCP的请求（类似telnet），该健康检查不影响源站服务情况。

如问题还未解决，请[提交工单](https://selfservice.console.aliyun.com/ticket/createIndex)。

## 日志的304状态码是什么原因？ {#section_ohl_cql_ilp .section}

客户端第一次向服务器成功发送请求，服务器会把内容正确返回给客户端，状态码是200，并会标记内容修改时间，和一个etag标记用来核实内容是否修改过，等下次同一客户端再次发送请求，会根据请求标记的修改时间和etag来判断文件内容在这期间是否修改过，如果没有修改过则返回304状态码，客户端直接加载web缓存内容，如果文件内容修改过则把最新内容返回给客户端，并返回最新文件修改时间和etag标记。

示例：

如下图所示，客户端第一次访问一个图片，请求成功后服务器返回200状态码，response响应包里会包含文件最近修改时间last-modified和etag标记。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/314939/156653574848445_zh-CN.png)

当客户端再次访问时，会在请求头带上上次读取内容的修改时间和etag标记，如下图，服务器会根据etag和last-modified判断文档内容最近有没有修改过，如若没有则返回304状态码，如若修改过则把最新内容返回客户端，状态码则是200。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/314939/156653574848446_zh-CN.png)

所以，有时候服务器日志、CDN日志、OSS日志出现304状态码，是正常现象，说明web缓存已经有这些内容了，并且在这期间这些内容并没有修改过，如果想更新web缓存，可以按ctrl+F5页面，客户端会清除本地web缓存从服务器发送请求，服务器则返回请求内容，并且状态码是200。

如问题还未解决，请[提交工单](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex)。

## 如何分析CDN访问日志？ {#section_fpd_8ri_7k7 .section}

在Linux环境下，您可以通过如下几个命令对CDN的访问日志进行分析：

-   查询状态为200的所有记录

     `grep -w "200" 日志文件名 |awk '{if($9=="206") print $0}' >200log.txt`

-   取文件中的某一列，例如是否hit：

     `cat 日志文件名 |awk '{print $12}'`

-   计算日志中responsesize：

     `cat 日志文件名 |awk 'BEGIN {size=0} {size=size+$11} END{print "endsizeis",size/1024/1024,"M"} '`

-   查询访问量前十的IP：

     `cat 日志文件名 | awk '{print $3}' |sort|uniq -c|sort -nr |head -10`


CDN日志字段说明，请参见[日志下载](intl.zh-CN/服务管理/日志管理/日志下载.md#)。

如问题还未解决，请[提交工单](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex)。

## 如何查询CDN节点的IP？ {#section_9p1_r9f_r2g .section}

您可以通过CDN控制台的诊断工具，确定IP是否为CDN节点IP。详细说明请参见[诊断工具](intl.zh-CN/服务管理/诊断工具.md#)。

如问题还未解决，请[提交工单](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex)。

