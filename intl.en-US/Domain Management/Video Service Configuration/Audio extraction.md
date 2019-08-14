# Audio extraction {#task_1664445 .task}

Audio extraction allows you to request the audio data in a video file. With audio extraction enabled, a CDN node extracts audio data from a video file and then returns only the audio data to the client. This reduces network traffic usage. This topic describes how to enable audio extraction.

When a client requests a video file, it sends a request to the CDN server. The request contains the URL of the video file, for example, `http://www.aliyun.com/test.flv?ali_audio_only=1`. After the CDN server receives the request, it returns the audio data in the video file to the client.

The client must support this transmission method: `Transfer-Encoding:chunked`.

1.  Log on to the [Alibaba Cloud CDN console](https://partners-intl.aliyun.com/login-required#cdn).
2.  In the left-side navigation pane, click **Domain Names**.
3.  On the Domain Names page, find the target domain name and click **Manage**.
4.  In the left-side navigation pane of the specified domain, click **Video**.
5.  Click the Audio Extraction switch to enable audio extraction. 

    After audio extraction is enabled, add the `ali_audio_only` parameter to the video file URL in a request to perform audio extraction. Audio extraction supports the following file formats:

    |Format|Metadata|ali\_audio\_only parameter|Example|
    |:-----|:-------|:-------------------------|:------|
    |MP4|Only MP4 video files with the metadata contained in their header support audio extraction. MP4 video files with the metadata contained in their footer do not support audio extraction.|Set the `ali_audio_only` parameter to 1 to require the CDN server to return only the metadata and audio data of the requested video. The video data is not returned. If you do not specify this parameter or set the parameter to other values, audio extraction is not performed.|`http: //domain/video.mp4? ali_audio_only=1`.|
    |FLV|No requirements.|Set the `ali_audio_only` parameter to 1 to require the CDN server to return only the metadata and audio data of the requested video. The video data is not returned. If you do not specify this parameter or set the parameter to other values, audio extraction is not performed.|`http:// domain/video.flv? ali_audio_only=1`.|


