# 刷新FAQ {#concept_269769 .concept}

-   [如何主动推送文件到CDN节点？](#section_pt8_7vj_8a7)
-   [CDN如何使用JAVA SDK刷新缓存？](#section_zj5_11c_aor)
-   [如何判断CDN的预热任务是否执行完成？](#section_9ni_ayq_8ol)
-   [CDN服务如何刷新文件？](#section_kp1_uui_147)

## 如何主动推送文件到CDN节点？ {#section_pt8_7vj_8a7 .section}

您可以通过CDN的预热功能，主动推送文件到CDN的2级节点上，这样当客户端访问相关url时，CDN的1级节点将直接从CDN的2级节点拉取数据，无需进行回源获取数据，具体配置方法请参见[配置刷新预热](intl.zh-CN/服务管理/刷新预热/配置刷新和预热.md#)。

## CDN如何使用JAVA SDK刷新缓存？ {#section_zj5_11c_aor .section}

CDN提供了JAVA、python、php、.Net等多种语言的SDK，详情请参见[SDK参考](../intl.zh-CN/SDK参考/SDK参考.md#)。

使用JAVA SDK刷新缓存的具体操作如下：

1.  引入SDK。

    请在pom.xml文件中增加以下依赖，准确的SDK版本号请参见[SDK参考](../intl.zh-CN/SDK参考/SDK参考.md#)。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/222601/156661499847741_zh-CN.png)

2.  初始化Client。

    SDK通过IAcsClient的instance来完成openapi的调用，因此在您发起调用前，请先初始化IAcsClient实例。示例代码如下：

    ``` {#codeblock_mpe_ect_hdq}
    public void init() throws ClientException {
            IClientProfile profile = DefaultProfile.getProfile("cn-hangzhou", "", "");
            client = new DefaultAcsClient(profile);
        }
    ```

3.  构造刷新请求。

    完整的示例代码如下：

    ``` {#codeblock_5x2_633_xfm}
    package aliyun.sdk.cdn;
    import com.aliyuncs.DefaultAcsClient;
    import com.aliyuncs.cdn.model.v20141111.RefreshObjectCachesRequest;
    import com.aliyuncs.exceptions.ClientException;
    import com.aliyuncs.exceptions.ServerException;
    import com.aliyuncs.http.HttpResponse;
    import com.aliyuncs.profile.DefaultProfile;
    import com.aliyuncs.profile.IClientProfile;
    public class cdntest {
    
        public static DefaultAcsClient client;
        public static void main(String[] args) throws ClientException {
            // TODO Auto-generated method stub
            init();
            RefreshObjectCaches();
        }
    
        public static void init() throws ClientException {
            IClientProfile profile = DefaultProfile.getProfile("cn-hangzhou",  "", "");
            client = new DefaultAcsClient(profile);
        }
    
        public static void RefreshObjectCaches() {
            RefreshObjectCachesRequest request = new RefreshObjectCachesRequest();
    
            //要刷新的URI
            request.setObjectPath("www.abc.com/abc/1.png");
            //刷新类型，默认是File
            request.setObjectType("File");
    
            try {
                HttpResponse httpResponse = client.doAction(request);
                System.out.println(httpResponse.getUrl());
                System.out.println(new String(httpResponse.getContent()));
                //todo something.
            } catch (ServerException e) {
                e.printStackTrace();
            } catch (ClientException e) {
                e.printStackTrace();
            }
        }
    }
    ```


如问题还未解决，请[提交工单](https://selfservice.console.aliyun.com/ticket/createIndex)。

## 如何判断CDN的预热任务是否执行完成？ {#section_9ni_ayq_8ol .section}

您可以通过访问具体URL时的Via头信息，判断预热是否成功。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/222601/156661499847744_zh-CN.png)

-   Via的前半部分代表二级节点状态，其中的`H`表示命中，说明文件已经预热到二级节点了，不需要再回源站了。
-   Via的后半部分代表一级节点的状态，`M`表示一级节点上没有缓存，需要向二级节点回源。

如问题还未解决，请[提交工单](https://selfservice.console.aliyun.com/ticket/createIndex)。

## CDN服务如何刷新文件？ {#section_kp1_uui_147 .section}

-   建议源站的内容不使用同名更新，以版本号的方式同步。
-   对于必须做同名更新的文件，您可以通过CDN控制台提交刷新任务，请参见[配置刷新预热](intl.zh-CN/服务管理/刷新预热/配置刷新和预热.md#)。

