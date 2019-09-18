# 刷新预热FAQ {#concept_269769 .concept}

本文为您介绍了刷新预热相关FAQ。

-   [如何主动推送文件到CDN节点？](#section_pt8_7vj_8a7)
-   [CDN如何使用JAVA SDK刷新缓存？](#section_zj5_11c_aor)
-   [如何判断CDN的预热任务是否执行完成？](#section_9ni_ayq_8ol)
-   [CDN服务如何刷新文件？](#section_kp1_uui_147)

## 如何主动推送文件到CDN节点？ {#section_pt8_7vj_8a7 .section}

您可以通过CDN的预热功能，主动推送文件到CDN的2级节点上，这样当客户端访问相关url时，CDN的1级节点将直接从CDN的2级节点拉取数据，无需进行回源获取数据，具体配置方法请参见[配置刷新预热](cn.zh-CN/服务管理/刷新预热/配置刷新和预热.md#)。

## CDN如何使用JAVA SDK刷新缓存？ {#section_zj5_11c_aor .section}

阿里云CDN为您提供了JAVA、Python、PHP、.Net等多种语言的SDK，详情请参见[阿里云SDK中心](https://developer.aliyun.com/tools/sdk)。

1.  引入SDK。

    请在`pom.xml`文件中添加以下依赖，准确的SDK版本号，详情请参见[阿里云SDK中心](https://developer.aliyun.com/tools/sdk)。

    ``` {#d7e58}
    <!--添加阿里云core依赖和cdn依赖-->
    <dependency>
       <groupId>com.aliyun</groupId>
       <artifactId>aliyun-java-sdk-cdn</artifactId>
       <version>3.0.10</version>
    </dependency>
    <dependency>
       <groupId>com.aliyun</groupId> 
       <artifactId>aliyun-java-sdk-core</artifactId>
       <version>4.1.0</version>
    </dependency>
    ```

2.  初始化Client。

    发起调用前，请先初始化IAcsClient实例。示例代码如下：

    ``` {#d7e67}
    DefaultProfile profile = DefaultProfile.getProfile("cn-hangzhou", "<accessKeyId>", "<accessSecret>");        
    IAcsClient client = new DefaultAcsClient(profile);
    ```

3.  构造刷新请求。

    完整的示例代码如下：

    ``` {#d7e76}
    import com.aliyuncs.DefaultAcsClient;
    import com.aliyuncs.IAcsClient;
    import com.aliyuncs.exceptions.ClientException;
    import com.aliyuncs.exceptions.ServerException;
    import com.aliyuncs.profile.DefaultProfile;
    import com.google.gson.Gson;
    import java.util.*;
    import com.aliyuncs.cdn.model.v20180510.*;
    
    public class RefreshObjectCaches {
        public static void main(String[] args) {
            DefaultProfile profile = DefaultProfile.getProfile("cn-hangzhou", "<accessKeyId>", "<accessSecret>");
            IAcsClient client = new DefaultAcsClient(profile);
    
            RefreshObjectCachesRequest request = new RefreshObjectCachesRequest();
            request.setObjectPath("www.abc.com/abc/1.png");
            request.setObjectType("File");
            try {
                RefreshObjectCachesResponse response = client.getAcsResponse(request);
                System.out.println(new Gson().toJson(response));
            } catch (ServerException e) {
                e.printStackTrace();
            } catch (ClientException e) {
                System.out.println("ErrCode:" + e.getErrCode());
                System.out.println("ErrMsg:" + e.getErrMsg());
                System.out.println("RequestId:" + e.getRequestId());
            }
        }
    }
    ```


如果问题还未解决，请[提交工单](https://selfservice.console.aliyun.com/ticket/createIndex)。

## 如何判断CDN的预热任务是否执行完成？ {#section_9ni_ayq_8ol .section}

您可以通过访问具体URL时的Via头信息，判断预热是否成功。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/222601/156877025547744_zh-CN.png)

-   Via的前半部分代表二级节点状态，其中的`H`表示命中，说明文件已经预热到二级节点了，不需要再回源站了。
-   Via的后半部分代表一级节点的状态，`M`表示一级节点上没有缓存，需要向二级节点回源。

如问题还未解决，请[提交工单](https://selfservice.console.aliyun.com/ticket/createIndex)。

## CDN服务如何刷新文件？ {#section_kp1_uui_147 .section}

-   建议源站的内容不使用同名更新，以版本号的方式同步。
-   对于必须做同名更新的文件，您可以通过CDN控制台提交刷新任务，请参见[配置刷新预热](cn.zh-CN/服务管理/刷新预热/配置刷新和预热.md#)。

