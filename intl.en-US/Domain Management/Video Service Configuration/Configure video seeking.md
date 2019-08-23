# Configure video seeking {#task_187634 .task}

You can configure video seeking to drag the slider in the progress bar to go to a particular location in the audio or video file. This topic describes video seeking and how to enable it.

Video seeking is applied to video-on-demand scenarios. When you drag the slider in the progress bar, the client will send a URL request similar to `http://www.aliyun.com/test.flv?start=10` to the server. The server returns the data from the keyframe before the 10th byte if start=10 is not the position of a keyframe.

-   Before configuring this feature, you must ensure that the origin server supports range requests. If the HTTP request header contains the range field, the origin server must be able to return 206 Partial Content.
-   The following table lists the supported file and URL formats.

    |File format|Meta information|start parameter|Example|
    |:----------|:---------------|:--------------|:------|
    |MP4|The meta information of a video file on the origin server must be contained in the file header and cannot be contained in the file tail.|The start parameter specifies the start time in seconds. Decimals are supported to indicate milliseconds. For example, start=1.01 indicates that the video is played from 1.01 seconds. If the frame at the time position specified by the start parameter is not a keyframe, CDN will find the keyframe before that time position.|The request URL `http: //domain/video.mp4? start=10` indicates that the video is played from the 10th second.|
    |FLV|Video files on the origin server must contain meta information.|The start parameter specifies a byte. If the byte specified by the start parameter is not a keyframe, CDN will automatically locate the keyframe before that byte.|``The request URL `http:// domain/video.flv? start=10` indicates that a video is played from the keyframe before the 10th byte, if start=10 is not the position of a keyframe.|


1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).
2.  In the left-side navigation pane, click **Domain Names**.
3.  On the Domain Names page, find the target domain name and click **Manage**.
4.  In the left-side navigation pane of the specified domain, click **Video**.
5.  In the Video Seeking section, enable video seeking. 

    ![Video seeking](images/7307_en-US.png)


