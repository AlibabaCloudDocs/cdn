# 域名管理FAQ {#concept_388554 .concept}

-   回源相关

    [如何解决在使用CDN+OSS组合过程中，静态文件强制下载的问题？](#section_z8f_rjo_68h)

-   缓存相关
    -   [CDN节点默认缓存策略是什么？](#section_p2p_shx_5ke)
    -   [使用CDN后，文件与源文件不一致，如何刷新缓存？](#section_325_ni7_ytc)
    -   [如何解决CDN下载文件不一致的问题？](#section_sra_dqj_thq)
    -   [关于CDN缓存方面的知识点有哪些？](#section_ao7_ncb_rfm)
    -   [导致CDN缓存命中率下降的因素有哪些？](#section_thc_zrh_nde)
    -   [CDN命中率低的原因是什么？](#section_mgq_9qw_7zi)
    -   [CDN如何设置某个目录或文件不缓存？](#section_fhq_sag_3i3)
    -   [如何通过浏览器审查元素判断CDN缓存是否成功？](#section_wk0_6l0_gb3)
    -   [如何设置Apache缓存策略？](#section_3pz_mdl_2l7)
    -   [如何设置服务器端的过期时间？](#section_hk9_mbl_hdc)
    -   [如何设置IIS缓存策略？](#section_l1c_ri4_rnp)
    -   [如何设置Nginx缓存策略？](#section_jj3_es7_7y4)
    -   [CDN如何处理源站的302跳转？](#section_tjm_owj_1nv)
    -   [CDN+OSS跨域访问失败的原因及处理方法是什么？](#section_m27_ze5_ufk)
    -   [为什么CDN加速导致CORS配置失效？](#section_7a5_vce_iij)
    -   [如何配置CDN支持CORS（跨域）？](#section_7vq_yjg_7sl)
    -   [使用CDN加速的网站如何设置CORS访问？](#section_rco_0wx_8od)
    -   [如何处理CDN回源流量较大的问题？](#section_j8x_aao_wch)
    -   [如何处理使用CDN后网站访问速度变慢的问题？](#section_8er_sl1_r28)
-   性能相关
    -   [CDN中GZIP压缩功能支持哪些格式？](#section_7ow_gn9_4x2)
    -   [为什么CDN加速后，源站本来有的ETag字段消失了？](#section_ekv_2bw_q4d)
    -   [站点接入到CDN以后，为什么元素加载不了？](#section_xge_gcx_jw8)
    -   [为什么CDN服务的回源流量大于访问流量？](#section_1qi_5de_ali)

## 如何解决在使用CDN+OSS组合过程中，静态文件强制下载的问题？ {#section_z8f_rjo_68h .section}

原因：由于OSS的某个策略，当访问默认三级域名时，会给文件加上attachment属性，从而使文件强制下载。

解决办法：将您的回源HOST类型修改为加速域名。具体配置步骤，请参见[设置回源HOST](cn.zh-CN/域名管理/回源配置/配置回源HOST.md#)。

如问题还未解决，请[提交工单](https://selfservice.console.aliyun.com/ticket/createIndex)。

## CDN节点默认缓存策略是什么？ {#section_p2p_shx_5ke .section}

-   缓存时间计算

    缓存时间为t，单位为秒。

    -   t =（savetime - last\_modified）\*0.1
    -   t = max（10，t）
    -   t = min（t，3600）
-   默认缓存规则

    -   当对象`Last-Modified`为`20140801 00:00:00`，当前时间为`20140801 00:01:00`， （curtime-Last\_modified）\*0.1=6s，那么缓存时间为10s，因为最小值为10s。
    -   当对象`Last-Modified`为`20140801 00:00:00`，当前时间为`20140802 00:00:00`，（curtime-Last\_modified）\*0.1=8640s，那么缓存时间为3600s。
    -   当对象`Last-Modified`为`20140801 00:00:00`，当前时间为`20140801 00:10:00`，（curtime-Last\_modified）\*0.1=60s，那么缓存时间为60s。
    -   如果源站没有`Last-Modified`响应头，但有`ETag`，则该对象极有可能是静态资源，将其默认缓存时间设置为`dft_expires`指令配置的最小值。
    -   如果源站没有`Last-Modified`，也没有`ETag`，则认为该对象为动态内容，将其默认缓存时间设置为0，每次都回源。
    **说明：** 

    -   因为网站开发及其相关技术人员更清楚自身网站的业务逻辑、静态和动态因素，所以建议您通过控制台根据文件类型和文件所在目录，设置缓存时间。详细说明，请参见[设置缓存过期时间](cn.zh-CN/域名管理/缓存配置/配置缓存过期时间.md#)。
    -   如果您已经配置了缓存策略，那么Cache的默认缓存策略不生效。

## 使用CDN后，文件与源文件不一致，如何刷新缓存？ {#section_325_ni7_ytc .section}

使用CDN产品后，如果遇到源站内容更新，并且使用旧URL发布给用户使用。需要在更新源站内容后，同时刷新CDN节点的缓存，这样才能保证源站内容与CDN的缓存内容保持一致。

如何刷新，请参见[配置刷新预热](../cn.zh-CN/服务管理/刷新预热/配置刷新和预热.md#)。

## 如何解决CDN下载文件不一致的问题？ {#section_sra_dqj_thq .section}

访问CDN上未过期的缓存，将直接返回该缓存资源。如果您对源站进行了同名更新，则访问时会发现请求到的资源仍然是旧的资源，导致网站内容错乱。建议您从如下几个方面解决该问题：

1.  建议您源站的内容不使用同名更新，而是以版本号的方式同步，即给URL增加版本参数，使CDN回源请求新资源。

    **说明：** 如果开启了过滤参数功能，则该方式无效。

2.  同名更新后，您可以通过CDN控制台或OpenAPI手动刷新对应资源的URL。如何刷新，请参见 [配置刷新预热](../cn.zh-CN/服务管理/刷新预热/配置刷新和预热.md#)。

    **说明：** 

    -   URL刷新主要适合于单个资源，刷新速度较快。
    -   目录刷新会刷新该目录下的所有文件，刷新速度较慢，且由于该目录下所有资源下次请求都会回源，因此可能会增加源站带宽压力。
3.  如果CDN的源站是OSS源站，您可以通过OSS控制台，开启CDN缓存刷新。这样就可以在OSS源站出现Object的同名更新时，调用CDN的刷新接口刷新对应的URL。详细说明，请参见[开启 CDN 缓存自动刷新](../../../../../cn.zh-CN/控制台用户指南/管理存储空间/管理域名/绑定CDN加速域名.md#cdncache)。

## 关于CDN缓存方面的知识点有哪些？ {#section_ao7_ncb_rfm .section}

-   CDN读取数据过程为：客户端 -\> CDN L1层 -\> CDN L2层 -\> 源站。当客户端访问您的源站资源时，客户端将先查看CDN的1级节点，再查找CDN的2级节点，如果2级节点没有，再查找源站。源站中的数据同步到2级节点，2级节点同步到1级节点，再从1级节点返回给客户端需要访问的数据。
-   CDN的刷新缓存，请参见[配置刷新预热](../cn.zh-CN/服务管理/刷新预热/配置刷新和预热.md#)。
-   CDN缓存规则的配置，请参见[设置缓存过期时间](cn.zh-CN/域名管理/缓存配置/配置缓存过期时间.md#)。
-   为了最优使用CDN服务，建议您将动静态页面进行域名分离，静态页面的域名使用CDN加速。
-   如果源站的cachecontrol、expires、lastmodify和etag都没设置，且CDN也没设置缓存规则，则CDN不进行缓存。
-   如果源站设置了no-cache、private、max-age = 0都遵循源站，则CDN不进行缓存。

## 导致CDN缓存命中率下降的因素有哪些？ {#section_thc_zrh_nde .section}

导致CDN缓存命中率下降的因素包括：

-   客户是否刷新过缓存？

    CDN的URL或目录刷新会清除CDN缓存，如果您刷新缓存，有可能造成短时间命中率下降。

-   带宽是否突增？并且访问的都是新的URL？

    带宽突增或者访问的新URL较多，会导致CDN节点回源较多，命中率会表现有下降趋势。

-   源站是否有新内容发布？

    CDN节点访问新内容，导致CDN节点回源较多，命中率会表现有下降趋势。

-   源站是否出现过异常？

    源站出现过异常，导致5XX和4XX增加，由于5XX和4XX不缓存，会表现命中率下降。

-   源站访问URL的header参数，或者在CDN控制管理后台的缓存配置规则是否改变过？

    调整缓存过期时间，有可能会带来命中率的变化。


## CDN命中率低的原因是什么？ {#section_mgq_9qw_7zi .section}

-   CDN数据流向：客户端 -\> CDN L1层 -\> CDN L2层 -\> 源站。阿里云CDN控制台统计的命中率仅仅是CDN L1层的命中率，实际上L2层的命中率数据也是从CDN节点获取的，并不会回源，所以真实的CDN命中率略高于控制台上显示的数据。
-   在您加速域名流量不高的情况下，即使未命中的URL不多，但是对命中率的统计计算影响很大。例如某CDN加速域名对外提供了10个可以访问的URL，其中有一个URL源站上设置了no-cache导致不缓存，即使其他URL访问都命中，命中率也仅有90%。
-   如果您源站上缓存header设置不当，或者缺少必要的header，根据CDN的缓存规则，这种情况下的缓存规则是不生效的，所以资源不缓存。

    **说明：** 

    -   缓存header设置不当主要指您在配置缓存规则中，将cache-control设置为no-cache/no-store/max-age=0/private或者将Pragma设置为no-cache，此时CDN执行不缓存。
    -   缺少必要的header指源站的response头中不包含etag和last-modified，这种情况也会导致不缓存。
    -   导致不缓存的详细信息，请参考[判断CDN不缓存某文件的方法](https://private-alipayobjects.alipay.com/alipay-rmsdeploy-image/skylark/docx/f987aa10-785c-4b48-8c17-84fc191ca562.docx)。
-   控制台设置了不缓存的规则。例如：某目录或者某种后缀的文件设置缓存时间为0秒。
-   源站动态内容多。目前CDN主要是加速静态资源（css、js、html、图片、txt、视频等），针对动态资源（php、jsp、包含内部逻辑处理甚至cookie等），基本都会回源。
-   CDN的访问URL中带有可变参数。例如：http://dccdn.pier39.cn/1.txt?timestamp=14378923中的timestamp表示时间戳，每次访问都会不同。CDN针对第一次访问的URL（之前未预热），无论该URL是否符合CDN的缓存规则，第一次访问都是未命中的，因为此时CDN节点还未缓存该文件。由于URL后面的参数可变，所以每次访问都是一个全新的URL，每次都会未命中，从而影响命中率。
-   刷新操作频繁，有定时刷新的操作。由于每次刷新都会导致所有已经在CDN上缓存的URL失效，那么下次访问同样的URL会未命中，从而影响命中率。
-   文件热度不够，不经常被客户访问到，导致被提前从CDN节点删除。CDN节点上缓存的文件，可以理解为按照热度属性采取末尾淘汰制，热度指该文件在该节点上被访问的频率，文件热度不够，一定程度上跟这个域名本身的流量不高有关系。

## CDN如何设置某个目录或文件不缓存？ {#section_fhq_sag_3i3 .section}

将目录或者文件的缓存时间设置为0即可，操作方法请参见[设置缓存过期时间](cn.zh-CN/域名管理/缓存配置/配置缓存过期时间.md#)。

## 如何通过浏览器审查元素判断CDN缓存是否成功？ {#section_wk0_6l0_gb3 .section}

开通CDN服务并配置完成后，如果您需要查看您的内容是否缓存到CDN上，请参考如下步骤：

1.  打开浏览器（以Chrome浏览器为例），打开开发者工具，在地址栏输入要查看的URL。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/314941/156653566048158_zh-CN.png)

2.  单击**Network**。
3.  单击访问的图片（要加速的内容），您可以查看请求（request）和返回（response）的详细报文信息。如下图：

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/314941/156653566048159_zh-CN.png)

    您需要注意如下三个字段：

    -   X-Swift-SaveTime：内容开始在CDN上缓存的时间。如上图，即2015-09-22 06:33:49开始在CDN缓存。由于系统时间是GMT时间，所以需要折算成北京时间，也就是2015-09-22 14:33:49开始缓存。
    -   X-Swift-CacheTime：CDN的默认缓存时间，以秒为单位。如上图中的86400，即缓存24小时。
    -   Age：内容在CDN上已经缓存的时间。如上图中的163s，即该内容已经在CDN缓存了163秒。根据时间，从2015-09-22 14:33:49开始缓存的，当前时间则为2015-09-22 14:36:32。您可以和电脑当前时间进行对比。

如问题还未解决，请[提交工单](https://selfservice.console.aliyun.com/ticket/createIndex)。

## 如何设置Apache缓存策略？ {#section_3pz_mdl_2l7 .section}

您可以通过apache的mod\_expires和mod\_headers两个模块设置Apache的缓存策略。

-   mod\_expires模块

    mod\_expires模块允许通过配置文件控制HTTP的Expires和Cache-Control头内容，它的主要作用是自动生成页面头部信息中的Expires标签和Cache-Control标签，从而降低客户端的访问频率和次数，达到减少不必要流量和增加访问速度的目的。

    mod\_expires是apache众多模块中配置比较简单的一个，它一共包括三条指令：

    -   ExpiresActive指令：打开或关闭产生`Expires:`和`Cache-Control:`头的功能。
    -   ExpiresByType指令：指定MIME类型的文档（如text或html）的过期时间。
    -   ExpiresDefault指令：默认所有文档的过期时间。
    过期时间的写法如下：

    ``` {#codeblock_1fy_fny_7lc}
    “access plus 1 month”
    “access plus 4 weeks”
    “now plus 30 days”
    “modification plus 5 hours 3 minutes”
    A2592000
    M604800
    ```

    **说明：** 

    -   `access`、`now`和`A`这三种写法的意义相同，都是指过期时间从访问时开始计算。
    -   `modification`和`M`的意义相同，指过期时间从被访问文件的最后修改时间开始计算。
    本种写法只对静态文件起作用，对由脚本生成的动态页面无效。配置实例：

    ``` {#codeblock_oac_aha_nnp}
     ExpiresActive On(开启mod_expires功能)
     ExpiresDefault "access plus 6 months"(默认的过期时间是6个月)
     ExpiresByType image/* "access plus 10 years"(图片的文件类型缓存时间为10年)
     ExpiresByType text/* "access plus 10 years"(文本类型缓存时间为10年)
     ExpiresByType application/* "access plus 30 minutes"(application文件类型缓存30分钟)
    ```

    验证： image/jpeg的缓存时间为315360000s（10年）。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/314941/156653566048164_zh-CN.png)

    如果将image/jpeg设置为不缓存（将max-age设置为0s）：

    ``` {#codeblock_nfq_fei_3g5}
    #ExpiresByType image/* "access plus 10 years"
    ExpiresByType image/*  A0
    ```

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/314941/156653566048165_zh-CN.png)

-   mod\_headers模块

    ``` {#codeblock_kad_zk4_uac}
     # YEAR
        Header set Cache-Control “max-age=2592000″
        # WEEK
        Header set Cache-Control “max-age=604800″
        # NEVER CACHE
        Header set Expires “Thu, 01 Dec 2003 16:00:00 GMT”
        Header set Cache-Control “no-store, no-cache, must-revalidate”
        Header set Pragma “no-cache”
    ```


如问题还未解决，请[提交工单](https://selfservice.console.aliyun.com/ticket/createIndex)。

## 如何设置服务器端的过期时间？ {#section_hk9_mbl_hdc .section}

过期时间控制支持三个维度，优先级依次为控制台设置 -\> 源站header设置 -\> cache的默认策略设置。

**说明：** 

-   关于控制台设置的详细说明，请参见[设置缓存过期时间](cn.zh-CN/域名管理/缓存配置/配置缓存过期时间.md#)。
-   关于cache的默认策略设置的详细说明，请参见[CDN节点默认缓存策略是什么？](#section_p2p_shx_5ke)。

Webserver缓存策略设置（源站设置）

1.  设置IIS缓存策略。详细说明，请参见[如何设置IIS缓存策略？](#section_l1c_ri4_rnp)。
2.  设置Nginx缓存策略。详细说明，请参见[如何设置Nginx缓存策略？](#section_jj3_es7_7y4)。
3.  设置Apache缓存策略。详细说明，请参见[如何设置Apache缓存策略？](#section_3pz_mdl_2l7)。

## 如何设置IIS缓存策略？ {#section_l1c_ri4_rnp .section}

设置IIS缓存策略的操作步骤如下：

1.  因为整体的站点只对.html、.jpg、.png、.gif、.apk等文件进行缓存，首先将整个站点设置成不缓存，具体操作如下：
    1.  打开IIS信息管理器，右键单击服务网站`a.cc.com`的属性。
    2.  单击**HTTP头**，勾选**启用内容过期**，选择**立即过期**，单击**确定**。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/314941/156653566148168_zh-CN.png)

2.  上述设置后，整个网站的内容都不会被CDN缓存，接着设置.html、.jpg、.png、.gif、.apk等文件类型的缓存策略。
    -   不同扩展名的文件都单独放在一个特定的目录下面，且该目录没有其他扩展名的文件。

        针对这个扩展名所在的整个目录设置缓存的时间。具体操作如下：

        1.  打开IIS信息管理器。
        2.  展开网站`a.cc.com`的目录，选中需要设置缓存时间的目录，如所有jpg文件都存储在img这个目录下，右键单击该目录并选择**属性**。
        3.  单击**HTTP头**。

            **说明：** 由于步骤1已经设置整个网站不缓存，所以此时**HTTP头**选项下的缓存设置和步骤1中的相同。

        4.  选择**此时间段后过期**，设置具体的过期时间，单击**确定**。

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/314941/156653566148171_zh-CN.png)

    -   特定扩展名的文件不是统一放在唯一的目录，而是和其他扩展名文件混合放在一个目录下。

        **说明：** 为了避免针对特定扩展名的文件进行逐个的配置，需要设置IIS支持通配符。

        以bin目录下的test.jpg为例，介绍缓存设置的操作步骤。

        1.  设置IIS支持通配符。
            1.  打开IIS信息管理器，右键单击服务网站`a.cc.com`的属性，选择**主目录**，单击**配置**。
            2.  在弹出的对话框中，单击**映射**，单击**插入**。

                ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/314941/156653566148172_zh-CN.png)

            3.  在弹出的对话框中，选择C: \\WINDOWS\\Microsoft.NET\\Framework\\v4.0.30319\\aspnet\_isapi.dll文件，单击**确定**。

                ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/314941/156653566148173_zh-CN.png)

                **说明：** 不勾选**确认文件是否存在**。

            4.  分别单击两个对话框中的**确定**，完成IIS通配符的支持配置。
        2.  在bin目录下，选择test.jpg并右键单击，选择**属性**。
        3.  单击**HTTP头**。
        4.  选择**此时间段后过期**，设置具体的过期时间，单击**确定**。
        5.  设置bin目录下其他相同扩展名文件的缓存时间，此时需要修改IIS的配置文件。具体操作如下：

            1.  用记事本程序打开IIS的配置文件，配置文件在C:\\WINDOWS\\system32\\inetsrv\\MetaBase.xml（IIS6的设置）目录下。
            2.  查找/bin/test.jpg，找到bin目录下test.jpg文件的缓存设置。
            3.  将test.jpg改为\*.jpg并保存。
            **说明：** 修改上述文件，需要在服务中关闭IIS admin Service。

        6.  其他扩展名的文件缓存设置操作同上。

如问题还未解决，请[提交工单](https://selfservice.console.aliyun.com/ticket/createIndex)。

## 如何设置Nginx缓存策略？ {#section_jj3_es7_7y4 .section}

HTTP头处理模块\(HTTP Headers\)允许设置任意的HTTP头，您可以使用add\_header和expires命令设置Nginx缓存策略。

|指令|语法|默认值|使用字段|
|--|--|---|----|
|add\_header|add\_header name value|none| -   http
-   server
-   location

 |
|expires **说明：** 这个指令控制是否在应答中标记一个过期时间以及如何标记。

 |expires \[time|epoch|max|off\] **说明：** 

-   Time：控制Cache-Control的值，负数表示no-cache。
-   epoch：将Expires头设置为1 January, 1970 00:00:01 GMT。
-   max：将Expires头设置为31 December 2037 23:59:59 GMT，将Cache-Control最大化到10年。
-   off：将禁止修改头部中的Expires和Cache-Control字段。

 |expires off| -   http
-   server
-   location

 |

通过expires设置，示例如下：

-   设置php的文件类型过期时间设置为1小时。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/314941/156653566248227_zh-CN.png)

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/314941/156653566248228_zh-CN.png)

-   设置php的文件类型为no-cache，cache服务器不缓存。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/314941/156653566248229_zh-CN.png)

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/314941/156653566248230_zh-CN.png)


通过add\_header设置，以动态的php文件设置为不缓存为例：

``` {#codeblock_ns3_em8_ldg}
location ~ .*\.php$ {
    if ($request_uri !~ ^/dynamicimg/) {
        add_header              Cache-Control "no-cache";
        add_header              Pragma no-cache;
    }
  }
```

如问题还未解决，请[提交工单](https://selfservice.console.aliyun.com/ticket/createIndex)。

## CDN如何处理源站的302跳转？ {#section_tjm_owj_1nv .section}

根据客户终端的设备，决定对应网站的前端界面样式是常见的网站设计需求。该需求的常见设计思路是，源站根据用户的请求，在源站对用户的请求做302跳转到对应的页面上进行服务。

在对网站部署CDN后，由于CDN的产品性质，CDN会对用户的访问资源缓存到CDN的节点上，以便后续可以加快用户的访问。这种情况下，可能会出现第一个用户访问后，对相应的302请求进行缓存。而其他不同终端设备的用户通过该URL进行访问时，就会出现访问到的仍然是第一个用户缓存的302请求到的页面。这就造成用户源站对不同终端设置的适配功能失效。

解决这种问题的思路是：

-   设置对第一个请求的URL不缓存，而对302跳转后的页面进行缓存。这样设置能够保证用户源站的终端配置功能生效的同时，也可以实现CDN对于页面的加速。CDN对于缓存的配置暂时支持目录和文件后缀名，用户可以结合这两种的缓存配置以及其优先级来根据自己的站点目录结构定义初始URL不缓存。
-   在源站对于初始页面设置不缓存，因为源站的不缓存策略对于CDN是具有最高优先级的。只要该页面的response中带有下述头信息，就能保证该页面不缓存。
    -   Cache-control:no-cache,no-store,private
    -   Cache-control:s-maxage=0,max-age=0
    -   pragma:no-cache

如问题还未解决，请[提交工单](https://selfservice.console.aliyun.com/ticket/createIndex)。

## CDN+OSS跨域访问失败的原因及处理方法是什么？ {#section_m27_ze5_ufk .section}

主要原因：

当您首次通过客户端浏览器访问资源时，如果CDN检测出该资源不存在，则回源进行访问。源站对比将数据，通过CDN返回给客户端浏览器。浏览器比对Access-Control-Allow-Origin后，允许正确，所以跨域正常。当您第二次访问资源时，CDN检测出存在该缓存资源，所以CDN将直接返回客户端缓存页面。由于CDN缓存了OSS未配置cors之前的文件及其头部，造成客户端浏览器判断失败，不允许访问，所以出现了跨域失败。

解决办法：

您可以通过设置Access-Control-Allow-Origin、Access-Control-Allow-Methods和Access-Control-Max-Age这三种HTTP头的参数的方式。如何设置，请参见[设置HTTP响应头](cn.zh-CN/域名管理/缓存配置/配置HTTP头.md#)。

设置完成后，只要您在CDN节点访问，就会包含上述3个头部信息，不会影响正常访问。验证结果如下：

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/314939/156653566348363_zh-CN.png)

如问题还未解决，请[提交工单](https://selfservice.console.aliyun.com/ticket/createIndex)。

## 为什么CDN加速导致CORS配置失效？ {#section_7a5_vce_iij .section}

原因：

由于CDN加速是通过将文件缓存在节点，由节点直接返回给您，达到加速效果的，如果缓存文件未过期，即使在源站对该文件进行了变更，您访问到的依旧是之前缓存在节点的内容，而不是更新后的内容。

因此，当开启了CDN加速功能或开启了图片处理功能（默认开启CDN加速功能）后，在CDN节点上已经被访问过的文件都将被缓存，此时若您配置或变更了cors配置，则CDN已缓存的内容不会自动同步该配置更新，从而导致cors不生效。

解决方案：

建议您在变更了cors配置后，进行相关URL的缓存刷新操作，以便cors配置能够及时生效。

-   通过控制台方式进行刷新的具体操作，请参见[配置刷新预热](../cn.zh-CN/服务管理/刷新预热/配置刷新和预热.md#)。
-   通过OpenAPI方式进行刷新的具体操作，请参见[RefreshObjectCaches](../cn.zh-CN/旧版API参考/刷新预热类接口/RefreshObjectCaches.md#)。

## 如何配置CDN支持CORS（跨域）？ {#section_7vq_yjg_7sl .section}

配置步骤：关于CORS的具体配置步骤，请参见[设置HTTP响应头](cn.zh-CN/域名管理/缓存配置/配置HTTP头.md#)。

注意事项：

-   目前不支持泛域名添加，如`*.12345.com`，仅支持域名精确匹配。
-   目前仅支持配置一条白名单域名。
-   若使用OSS产品作为源站，OSS与CDN平台同时配置CORS，CDN的配置将覆盖OSS。
-   若源站为您的服务器或ECS产品，建议先进行动静分离，静态文件使用CDN加速，CDN控制台配置的CORS功能，仅对静态文件生效。

## 使用CDN加速的网站如何设置CORS访问？ {#section_rco_0wx_8od .section}

网站使用CDN加速后，如果某个CDN节点先发生了非跨域的访问，CDN会缓存一个没有CORS头部的文件内容，在过期之前发生的跨域访问，会因为没有CORS头部信息而导致访问报错。您可以通过自定义Header的方式设置CORS的头部信息，避免这种情况的发生。

自定义Header的具体操作步骤，请参见[设置HTTP响应头](cn.zh-CN/域名管理/缓存配置/配置HTTP头.md#)。

如问题还未解决，请[提交工单](https://selfservice.console.aliyun.com/ticket/createIndex)。

## 如何处理CDN回源流量较大的问题？ {#section_j8x_aao_wch .section}

原因：

-   缓存命中率差，那么回源流量较大（一般缓存命中率建议在90%及以上）。
-   缓存命中率高，CDN总流量基数大，那么回源流量相对来说也较大。

对于缓存命中率差的情况，解决方法如下：

-   增加目录缓存。详细说明，请参见[设置缓存过期时间](cn.zh-CN/域名管理/缓存配置/配置缓存过期时间.md#)。

    **说明：** 

    -   为了确保其他未设置缓存规则的文件都能缓存命中，建议该条缓存规则设置在最下方。
    -   对于不需要缓存的，建议源站设置nocache，但不建议过多的文件设置nocache，过多的文件回源会影响加速效果。
-   排查CDN日志定位缓存总是不命中的文件。详细说明，请参见[日志下载](../cn.zh-CN/服务管理/日志管理/日志下载.md#)。
-   通过Google Chrome浏览器的开发者工具，定位缓存不命中的元素，排查每个元素的response头。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/328745/156653566348315_zh-CN.png)

    **说明：** 

    -   X-cache：表示缓存是否命中。其中，MISS表示不命中。Hit表示命中。
    -   X-Swift-CacheTime：表示会在CDN一级节点中缓存多长时间。
    -   X-Swift-SaveTime:Tue, 15 Dec 2015 11:25:26 GMT：表示该资源缓存的具体时间点。
    从图中可以看出，由于Cache-Control的值为no-cache，所以该资源缓存不命中。如果Cache-Control的值为private，也不能缓存命中。您可以定位该资源是否可以缓存，如果可以，请取消nocache。

-   CDN只对get请求进行缓存，对于非get请求的资源，建议进行域名分离，只对静态资源进行CDN加速。

如问题还未解决，请[提交工单](https://selfservice.console.aliyun.com/ticket/createIndex)。

## 如何处理使用CDN后网站访问速度变慢的问题？ {#section_8er_sl1_r28 .section}

CDN服务的主要功能是进行网站访问加速，出现使用CDN后的访问速度反而变慢的常见场景有两种场景。

-   缓存命中率不高

    影响缓存命中率的常见原因如下：

    -   缓存配置的问题。
    -   频繁的刷新UR或者目录缓存。
    -   Http Header导致无法缓存。
    -   刚添加，缓存的文件还不多。
    -   网站访问量低，过期时间短，命中的文件少。
-   局部地区访问速度较慢，个别区域动态文件回源较慢。

    资源文件缓存到CDN后，CDN访问就会比源站访问快些的。对于这种情况，您可以按如下排查步骤进行定位。

    1.  测试域名解析是否正确，确保您的应用已经正常解析到CDN上。
    2.  测试域名进行访问，通过浏览器的开发者工具，测试静态页面是否已经缓存，主要看x-catch是否已经hit。hit说明已经命中，miss说明没有被缓存。
    3.  查看已经缓存的静态文件的加载时间，并通过截图标注。
    4.  将域名绑定到本地的hosts文件后，重复步骤3进行验证，对比两次的访问时间。

如问题还未解决，请[提交工单](https://selfservice.console.aliyun.com/ticket/createIndex)。

## CDN中GZIP压缩功能支持哪些格式？ {#section_7ow_gn9_4x2 .section}

目前阿里云CDN支持GZIP压缩的内容格式如下：

-   content-type：text/xml
-   content-type：text/plain
-   content-type：text/css
-   content-type：application/javascript
-   content-type：application/x-javascript
-   content-type：application/rss+xml
-   content-type：text/javascript
-   content-type：image/tiff
-   content-type：image/svg+xml
-   content-type：application/json

**说明：** 

-   源站上的资源大小需要超过1024B，才能进行GZIP压缩。
-   Internet Explorer6对GZIP的兼容性较差，如果有Internet Explorer6的访问需求，不建议您开启GZIP压缩功能。

如问题还未解决，请[提交工单](https://selfservice.console.aliyun.com/ticket/createIndex)。

## 为什么CDN加速后，源站本来有的ETag字段消失了？ {#section_ekv_2bw_q4d .section}

由于Nginx的默认行为：如果同时开启gzip和ETag，则直接不用ETag。

当您遇到这种情况时，建议排查是否开启了gzip功能。

## 站点接入到CDN以后，为什么元素加载不了？ {#section_xge_gcx_jw8 .section}

原因：可能CDN对应的加速域名开启了过滤参数功能。

解决办法：关闭过滤参数功能。详细说明，请参见[过滤参数](cn.zh-CN/域名管理/性能优化/过滤参数.md#)。

## 为什么CDN服务的回源流量大于访问流量？ {#section_1qi_5de_ali .section}

如果在使用CDN服务时，出现了回源流量大于访问流的情况，如下图：

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/328745/156653566348289_zh-CN.png)

这类问题一般是由于源站未开启Gzip压缩，CDN开启了Gzip压缩导致的。

对于文本等类型的内容，Gzip的压缩比较高，所以如果源站没有开启Gzip压缩，但是客户访问CDN时，CDN进行了Gzip压缩，就可能会出现CDN回源带宽比访问带宽还高的情况，所以建议在源站上开启Gzip功能。

此外，由于使用CDN时，会添加一些CDN必须使用的header信息，如Via的header，即使源站已经设置了Gzip，如下图：

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/328745/156653566348290_zh-CN.png)

但是当在请求中带有Via的header时，源站可能会无法正确的响应Gzip，如下图：

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/328745/156653566448291_zh-CN.png)

针对这种情况，建议在源站设置全部开启Gzip的规则。以nginx为例，可以进行如下设置：

 `gzip_proxied any;` 

其它的web服务，请参考进行类似的修改。

如问题还未解决，请[提交工单](https://selfservice.console.aliyun.com/ticket/createIndex)。

## CDN基础配置中的过滤参数有什么作用？ {#section_95c_pkw_n90 .section}

开启过滤参数的作用：忽略URL请求中`?`后面的参数，提高CDN缓存的命中率。

-   开启过滤参数功能后，访问URL无需匹配`?`后面的参数，就可命中CDN的缓存，提高CDN的命中率。

    示例：第一次访问`http://www.****.com/1.jpg`时，CDN没有缓存，直接回源访问数据。第二次访问`http://www.****.com/1.jpg?test1`，由于开启了过滤参数，所以`?`后面的参数无需匹配，即可命中CDN缓存`http://www.****.com/1.jpg`。后续访问时，无论`?`后面带的是什么参数，都命中缓存`http://www.****.com/1.jpg`。

-   关闭过滤参数功能后，访问URL需精确匹配`?`后面的参数，提高请求的精确性。

    示例：第一次访问`http://www.****.com/1.jpg`时，CDN没有缓存，直接回源访问数据。第二次访问`http://www.****.com/1.jpg?test1`，由于关闭了过滤参数，所以`?`后面的参数需精确匹配，即无法响应CDN缓存内容`http://www.****.com/1.jpg`需要重新回源获取`http://www.****.com/1.jpg?test1`。后续访问时，需要精确匹配`?`后面的参数，才能响应CDN缓存内容。


如问题还未解决，请[提交工单](https://selfservice.console.aliyun.com/ticket/createIndex)。

