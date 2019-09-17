# CDN使用JAVA SDK刷新缓存示例代码 {#concept_mbf_42t_xdb .concept}

本文为您介绍了CDN使用JAVA SDK刷新缓存。

阿里云CDN为您提供了JAVA、Python、PHP、.Net等多种语言的SDK，详情请参见[阿里云SDK中心](https://developer.aliyun.com/tools/sdk)。

使用JAVA SDK刷新缓存的示例代码如下所示。

1.  引入SDK。

    请在`pom.xml`文件中添加以下依赖，准确的SDK版本号，详情请参见[阿里云SDK中心](https://developer.aliyun.com/tools/sdk)。

    ``` {#codeblock_3pq_1es_y5z}
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

    ``` {#codeblock_da4_5nd_0fm}
    DefaultProfile profile = DefaultProfile.getProfile("cn-hangzhou", "<accessKeyId>", "<accessSecret>");        
    IAcsClient client = new DefaultAcsClient(profile);
    ```

3.  构造刷新请求。

    完整的示例代码如下：

    ``` {#codeblock_607_3dh_vn4}
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


如果问题还未解决，请联系[售后技术支持](https://selfservice.console.aliyun.com/ticket/createIndex.htm)。

