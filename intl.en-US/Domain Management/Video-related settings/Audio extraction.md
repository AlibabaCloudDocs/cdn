# Audio extraction

After the audio extraction feature is enabled, Content Delivery Network \(CDN\) nodes extract audio data from a video file and then return only the audio data to the client. This reduces data usage. This topic describes how to enable audio extraction.

When a client requests a video file, the client sends a request to the nearest CDN node. The request contains the URL of the video file, for example, `http://www.aliyun.com/test.flv?ali_audio_only=1`. After the CDN node receives the request, it returns the audio data extracted from the video file to the client.

The client must support the following transmission method: `Transfer-Encoding:chunked`.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the Domain Names page, find the target domain name and click **Manage**.

4.  In the left-side navigation pane of the specified domain, click **Video**.

5.  In the **Audio Extraction** section, turn on the Audio Extraction switch.

    After audio extraction is enabled, requests sent from clients must include the `ali_audio_only` parameter to extract audio data. The following table describes the file formats supported by audio extraction.

    |Format|Metadata|ali\_audio\_only|Example|
    |:-----|:-------|:---------------|:------|
    |MP4|The metadata of a video file on the origin server must be contained in the file header and cannot be contained in the file tail.|Set the `ali_audio_only` parameter to 1 to require Alibaba Cloud CDN to return only the metadata and audio data of the requested video file. The video data is not returned. If requests do not include this parameter or it is set to other values, audio extraction is not performed.|`http: //domain/video.mp4? ali_audio_only=1`|
    |FLV|No requirements.|Set the `ali_audio_only` parameter to 1 to require Alibaba Cloud CDN to return only the metadata and audio data of the requested video file. The video data is not returned. If requests do not include this parameter or it is set to other values, audio extraction is not performed.|`http:// domain/video.flv? ali_audio_only=1`|


