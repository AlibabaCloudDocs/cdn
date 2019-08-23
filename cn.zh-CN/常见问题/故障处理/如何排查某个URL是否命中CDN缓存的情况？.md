# 如何排查某个URL是否命中CDN缓存的情况？ {#concept_711183 .concept}

使用CDN后，您可以通过浏览器进行简单的访问测试，查看访问网站是否命中CDN缓存。具体方法如下：

1.  使用Chrome或者火狐浏览器，在浏览器界面，按F12打开浏览器调试界面，然后选择网络或Network。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/328745/156655188648301_zh-CN.png)

2.  访问一个网站链接，查看响应头信息中的`X-Cache`字段。
    -   显示MISS，说明没有命中CDN缓存，是回源的。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/328745/156655188748302_zh-CN.png)

    -   显示HIT，说明命中了CDN缓存。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/328745/156655188748303_zh-CN.png)


如问题还未解决，请[提交工单](https://selfservice.console.aliyun.com/ticket/createIndex)。

