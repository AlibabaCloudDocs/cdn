# Video seeking {#task_187634 .task}

With video seeking enabled, you can seek to a specified position when you play video and audio. This topic describes how to configure video seeking.

With video seeking enabled, if you seek to a specified position when you play video or audio on demand, the client sends a request to the server. The request contains the URL of the video or audio file, for example, `http://www.aliyun.com/test.flv?start=10`. The start parameter specifies the position that you want to seek to. After the server receives the request, it seeks to the keyframe at the specified position and then returns the content starting from this keyframe. If no keyframe can be found at the specified position, the server seeks to the last keyframe before the specified position.

-   Before you configure video seeking, make sure that the origin site supports HTTP range requests. If an HTTP request contains the Range field in its header, then an origin site must return a 206 partial content status message.
-   The file formats supported by video seeking and the sample URLs are as follows:

    |File format|Metadata|Start parameter|Example|
    |:----------|:-------|:--------------|:------|
    |MP4|Only MP4 video files with the metadata contained in their header support video seeking. MP4 video files with the metadata contained in their footer do not support video seeking.|The start parameter specifies the time that you want to seek to, in seconds. Milliseconds are expressed with decimals. For example, start=1.01 represents 1.01 second. If CDN cannot find the keyframe at the time specified by start, it seeks to the last keyframe before the specified time.|The request URL `http: //domain/video.mp4? start=10` is to seek forward by 9 seconds.|
    |FLV|FLV video files must contain metadata.|The start parameter specifies the byte that you want to seek to. If CDN cannot find the keyframe at the byte specified by the start parameter, it seeks to the last keyframe before the specified byte.|For video file `http: //domain/video.flv`, the request URL `http:// domain/video.flv? start=10` is to seek to the tenth byte. If no keyframe can be found at the tenth byte, then CDN seeks to the last keyframe before the tenth byte.|


1.  Log on to the [Alibaba Cloud CDN console](https://partners-intl.aliyun.com/login-required#cdn).
2.  In the left-side navigation pane, click **Domain Names**.
3.  On the Domain Names page, find the target domain name and click **Manage**.
4.  In the left-side navigation pane of the specified domain, click **Video**.
5.  Click the Video Seeking switch under Video Seeking to enable the function. 

    ![Enable video seeking](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5156/156715437155223_en-US.png)

6.  Click the Time-based FLV Seeking switch to enable the function.
7.  Click **Modify**. 

    ![Modify video seeking parameters](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5156/156715437155249_en-US.png)

8.  Set the Start Parameter and End Parameter for video seeking.
9.  Click **OK**.

