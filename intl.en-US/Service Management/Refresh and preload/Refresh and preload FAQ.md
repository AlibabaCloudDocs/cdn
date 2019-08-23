# Refresh and preload FAQ {#concept_269769 .concept}

-   [How can I actively preload files to a CDN node?](#section_pt8_7vj_8a7)
-   [How does CDN use the JAVA SDK to refresh the cache?](#section_zj5_11c_aor)
-   [How can I identify whether a CDN preload task is complete?](#section_9ni_ayq_8ol)
-   [How can I use CDN to refresh files?](#section_kp1_uui_147)

## How can I actively preload files to a CDN node? {#section_pt8_7vj_8a7 .section}

You can actively preload files to a CDN L2 node by using the preload feature. As a result, when a client visits a relevant URL, the CDN L1 node will retrieve data directly from the CDN L2 node without requesting data from the origin. For more information about the preload feature, see [EN-US\_TP\_5168.md\#](reseller.en-US/Service Management/Refresh and preload/Refresh and Preload.md#).

## How does CDN use the JAVA SDK to refresh the cache? {#section_zj5_11c_aor .section}

Alibaba Cloud CDN provides SDKs for multiple languages including JAVA, Python, PHP, and .NET. For more information, see [SDK Reference](../reseller.en-US/Developer Guide/SDK Reference.md#).

To use the JAVA SDK to refresh the cache, follow these steps:

1.  Import the SDK to your project.

    Add the following dependencies to the pom. xml file. For more information about SDK versions, see [SDK Reference](../reseller.en-US/Developer Guide/SDK Reference.md#).

    ![](images/47741_en-US.png)

2.  Initialize the client.

    The SDK uses an IAcsClient instance to call the API. Therefore, before you initiate a call, initialize the IAcsClient instance. Sample code is as follows.

    ``` {#codeblock_mpe_ect_hdq}
    public void init() throws ClientException {
            IClientProfile profile = DefaultProfile.getProfile("cn-hangzhou", "", "");
            client = new DefaultAcsClient(profile);
        }
    ```

3.  Construct a refresh request.

    A complete sample code is as follows.

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
    
            //The URI to refresh.
            request.setObjectPath("www.abc.com/abc/1.png");
            //The object type to refresh. The default value is File.
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


If the issue still persists, .

## How can I identify whether a CDN preload task is complete? {#section_9ni_ayq_8ol .section}

After you send a preload request to a URL, you can check the Via header in the received response to identify whether the preload task is complete.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/222601/156655276147744_en-US.png)

-   The first half of the Via header indicates the status of the L2 node. The `H` field indicates a hit. This indicates that the specified content has been preloaded to the L2 node and that you do not need to request the content from the origin.
-   The second half of the Via header represents the status of the L1 node. The `M` field indicates that no cache is available on the L1 node and that the L1 node needs to request the content from the L2 node.

If the issue still persists, .

## How can I use CDN to refresh files? {#section_kp1_uui_147 .section}

-   We recommend that you synchronize files of the origin by using version numbers instead of file names.
-   To synchronize files that must be updated with the same name, submit a refresh task in the CDN console. For more information, see [EN-US\_TP\_5168.md\#](reseller.en-US/Service Management/Refresh and preload/Refresh and Preload.md#).

