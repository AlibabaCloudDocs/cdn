# Make API calls to accelerate content delivery outside mainland China

This topic describes how to call the AddCdnDomain operation to add a domain name to Alibaba Cloud Content Delivery Network \(CDN\) to accelerate content delivery in accelerated regions outside mainland China.

Before you call this operation, complete the following steps:

-   [Create an Alibaba Cloud account](https://account.alibabacloud.com/register/intl_register.htm)
-   [Complete real-name verification](https://www.alibabacloud.com/help/doc-detail/52595.htm)
-   [Activate Alibaba Cloud Content CDN](/intl.en-US/Acceleration in Hong Kong (China), Macao (China), Taiwan (China), and regions outside China/Configure CDN acceleration/Configure Alibaba Cloud CDN in accelerated regions outside mainland China in the CDN console.md)
-   [Use Alibaba Cloud SDK for Java](https://www.alibabacloud.com/help/doc-detail/66496.htm)

Alibaba Cloud CDN applies to a wide array of scenarios, including but not limited to:

-   Small image files: Your websites or applications offer downloads of images and small files in formats such as HTML, CSS, and JavaScript.
-   Large files: Your websites or applications offer downloads of files larger than 20 MB, such as game applications, client applications, and mobile apps.
-   On-demand audio and video streaming: Your websites or applications offer on-demand video streaming or short video streaming. Mainstream media formats such as MP4 and FLV are supported.

If your workloads are deployed in one of the preceding scenarios, and the origin server is deployed in a region outside mainland China, perform the following steps to configure Alibaba Cloud CDN:

1.  Add Maven dependencies.

    **Note:** The SDK used in this example may not be the latest version. For more information about the latest version, visit the [Alibaba Cloud Open Platform](https://open.aliyun.com/sdk).

    ```
    <dependency>
        <groupId>com.aliyun</groupId>
        <artifactId>aliyun-java-sdk-cdn</artifactId>
        <version>3.0.10</version>
    </dependency>
    <dependency>
        <groupId>com.aliyun</groupId>
        <artifactId>aliyun-java-sdk-core</artifactId>
        <version>4.4.4</version>
    </dependency>
    ```

2.  Call the AddCdnDomain operation.

    The endpoint of an Object Storage Service \(OSS\) bucket is added to Alibaba Cloud CDN in this example. The accelerated region is set to global. The OSS bucket delivers images and small files. For more information about the API operation, see [AddCdnDomain](/intl.en-US/New API Reference/Domain name management/AddCdnDomain.md).

    **Note:** If your CDN service is deployed outside mainland China, select global or global \(excluding mainland China\) as the accelerated region. When you select global as the accelerated region, the accelerated domain name must obtain an Internet Content Provider \(ICP\) number.We recommend that you apply for an ICP number through Alibaba Cloud ICP Filing System.

    ```
    import com.aliyuncs.DefaultAcsClient;
    import com.aliyuncs.IAcsClient;
    import com.aliyuncs.exceptions.ClientException;
    import com.aliyuncs.exceptions.ServerException;
    import com.aliyuncs.profile.DefaultProfile;
    import java.util.*;
    import com.aliyuncs.cdn.model.v20180510.*;
    
    public class AddCdnDomain {
        public static void main(String[] args) {
            // Specify your AccessKey ID and AccessKey secret.
            DefaultProfile profile = DefaultProfile.getProfile("cn-hangzhou", "<accessKeyId>", "<accessSecret>");
            IAcsClient client = new DefaultAcsClient(profile);
    
            AddCdnDomainRequest request = new AddCdnDomainRequest();
            request.setRegionId("cn-hangzhou");
            request.setCdnType("web");
            request.setDomainName("****.aliyun.com");
            request.setSources("[{\"content\":\"test.oss-cn-hangzhou.aliyuncs.com\",\"type\":\"oss\",\"priority\":\"20\",\"port\":80,\"weight\":\"15\"}]");
            //Select the accelerated region. If the accelerated region is outside mainland China, enter global or overseas.
            request.setScope("global");
            try {
                AddCdnDomainResponse response = client.getAcsResponse(request);
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


If the API call is successful, the system returns a request ID to you.

```
{ 
  "RequestId": "0AEDAF20-4DDF-4165-8750-47FF9C1929C9" 
}
```

You can log on to the Alibaba Cloud CDN console to view the accelerated domain name and configure a CNAME record for the domain name. For more information about what to do next, see [Configure a CNAME record](/intl.en-US/Acceleration in Hong Kong (China), Macao (China), Taiwan (China), and regions outside China/Configure CDN acceleration/Configure Alibaba Cloud CDN in accelerated regions outside mainland China in the CDN console.md).

