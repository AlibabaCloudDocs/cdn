# Audio extraction

After the audio extraction feature is enabled, Alibaba Cloud Content Delivery Network \(CDN\) nodes extract audio data from a video file and then return only the audio data to clients. This reduces bandwidth and data usage. This topic describes how to enable audio extraction.

When a client requests a video file, the client sends a request to the nearest CDN node. The request contains the URL of the video file, for example, `http://www.aliyun.com/test.flv?ali_audio_only=1`. Then, the CDN node returns the audio data extracted from the video file to the client. The client must support the following transmission method: `Transfer-Encoding: chunked`.

**Note:**

-   The audio extraction feature does not support range requests. Browsers such as Safari initiate a range request when a user plays a video. We recommend that you provide user-developed clients to your users for extracting audio data.
-   If you also want to allow users to seek audio or video content, configure the audio or video seeking feature. When a client seeks through a video file, the client reads the metadata of the video file to determine the total length of the video file. The video file can be sought based on the length of the video file. For more information, see [Configure video seeking](/intl.en-US/Domain Management/Video-related settings/Configure video seeking.md).
-   Audio extraction does not support MP4 files whose box header size is 16 \(64 bits\). It only supports MP4 files whose box header size is 8.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the management pane of the domain name, click **Video**.

5.  In the **Audio Extraction** section, turn on Audio Extraction.

    After audio extraction is enabled, requests sent from clients must include the `ali_audio_only` parameter to extract audio data. The following table describes the file formats supported by audio extraction.

    |File format|Metadata|ali\_audio\_only|Example|
    |:----------|:-------|:---------------|:------|
    |MP4|The metadata of a video file on the origin server must be contained in the file header and cannot be contained in the file tail.|Set the `ali_audio_only` parameter to 1 to require Alibaba Cloud CDN to return only the metadata and audio data of the requested video file. The video data is not returned. If requests do not include this parameter or it is set to other values, audio extraction is not performed.|`http: //domain/video.mp4?ali_audio_only=1`.|
    |FLV|No requirements.|Set the `ali_audio_only` parameter to 1 to require Alibaba Cloud CDN to return only the metadata and audio data of the requested video file. The video data is not returned. If requests do not include this parameter or it is set to other values, audio extraction is not performed.|`http:// domain/video.flv?ali_audio_only=1`.|


**Related topics**  


[BatchSetCdnDomainConfig](/intl.en-US/New API Reference/Domain name management/BatchSetCdnDomainConfig.md)

