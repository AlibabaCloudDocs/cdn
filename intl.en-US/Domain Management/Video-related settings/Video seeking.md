---
keyword: [seek, video seeking]
---

# Video seeking

Video seeking allows users to seek a specified position without the need to compromise the playback quality when they play video or audio content. This topic describes how to configure video seeking.

After video seeking is enabled, when a user seeks a specified position on the video or audio content on demand, the client sends a request to the server. The request contains the URL of the video or audio file, for example, `http://www.aliyun.com/test.flv?start=10`. The start parameter specifies the position that the user wants to seek. After the server receives the request, it seeks the keyframe at the specified position and then returns the content that starts from this keyframe. If no keyframe can be found at the specified position, the server seeks the last keyframe before the specified position.

Before you configure video seeking, make sure that the origin server supports HTTP range requests. If an HTTP request includes the Range header field, the origin server returns an HTTP 206 status code \(partial content message\).

The following table describes the file formats supported by video seeking.

|File format|Metadata|Start parameter|Example|
|:----------|:-------|:--------------|:------|
|MP4|The metadata of a video file on the origin server must be contained in the file header and cannot be contained in the file tail.|The start parameter specifies the position. If the position specified by the start parameter is not a keyframe, Alibaba Cloud Content Delivery Network \(CDN\) automatically locates the last keyframe before the specified position. The start parameter supports only values in seconds. Decimals are supported. For example, if you specify start=1.01, the position is at 1.01 seconds after the video file starts.|The request URL `http://domain/video.mp4?start=10` specifies that the video is played from the 10th second.|
|FLV|Video files on the origin server must contain metadata.|The start parameter specifies the byte. If the byte specified by the start parameter is not a keyframe, Alibaba Cloud CDN automatically locates the last keyframe before the specified byte.|The request URL `http:// domain/video.flv?start=10` specifies that the video is played from the 10th byte.|

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the management pane of the domain name, click **Video**.

5.  In the **Video Seeking** section, turn on **Video Seeking**.

6.  Optional. Allow FLV files to be sought by time.

    Turn on **Time-based FLV Seeking**. After you enable this feature, FLV files can be sought by time.

7.  Optional. Specify the start and end time parameter names.

    1.  Click **Modify** on the right side of **Custom Parameters**.

    2.  In the **Customize Parameters for Video Seeking** dialog box, set Start Parameter and End Parameter.

        **Note:**

        -   The default name of the start parameter is start and the end parameter is end.
        -   Parameter names can contain letters, digits, and underscores \(\_\). Examples: 123, aabbAABB, and aa\_BB123.
    3.  Click **OK**.


**Related topics**  


[BatchSetCdnDomainConfig](/intl.en-US/New API Reference/Domain name management/BatchSetCdnDomainConfig.md)

