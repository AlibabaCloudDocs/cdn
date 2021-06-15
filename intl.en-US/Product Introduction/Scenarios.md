---
keyword: scenario
---

# Scenarios

Alibaba Cloud Content Delivery Network \(CDN\) is applicable to a wide array of scenarios. You can use Alibaba Cloud CDN to accelerate the delivery of images, small files, large files, and on-demand video and audio content. This topic describes the scenarios supported by Alibaba Cloud CDN.

## Scenarios

The following table describes the scenarios supported by Alibaba Cloud CDN.

|Scenario|Description|
|--------|-----------|
|[Image and small file distribution](#section_mnp_tw0_fz3)|Accelerates the delivery of small files on websites and applications. Examples of the websites and applications include web portals, e-commerce websites, news websites and applications, and gaming and other entertainment websites.|
|[Large file distribution](#section_9n4_tgj_a76)|Accelerates the delivery of files that are larger than 20 MB, such as game installation packages, application updates, ROM updates, and application packages.|
|[On-demand audio and video streaming](#section_zuc_giw_6og)|Accelerates the delivery of audio and video content on websites and applications, such as film and television websites, online education websites, news websites, and short video websites. Mainstream formats, including MP4 and FLV, are supported.|

## Image and small file distribution

Alibaba Cloud CDN accelerates the delivery of small files on websites and applications. Examples of the websites and applications include web portals, e-commerce websites, news websites and applications, and gaming and other entertainment websites. You must separate static content from dynamic content on your origin server. The delivery of static content, such as images, CSS files, and small JavaScript files, is accelerated by Alibaba Cloud CDN. The delivery of dynamic content is accelerated by [Dynamic Route for CDN \(DCDN\)](https://www.alibabacloud.com/zh/product/dcdn). For more information about static and dynamic content, see [What are static content and dynamic content?]()

This feature addresses the following issues:

-   Websites respond slowly because they contain a large number of small files.
-   The web page loading speed and the quality of web services differ across regions.
-   During promotions, the origin servers may become unavailable due to traffic spikes. In this case, services are interrupted.
-   Images cannot be compressed or optimized to meet client requirements due to complex processing of image formats and resolution.

## Large file distribution

Alibaba Cloud CDN accelerates the delivery of files that are larger than 20 MB, such as game installation packages, application updates, ROM updates, and application packages.

This feature addresses the following issues:

-   Users cannot download files, or the download speed is low.
-   Downloads may be interrupted due to unstable network connections. If users download the data again, additional data transfer is required.
-   A website is vulnerable to hijacking or hotlink attacks, which can cause business loss.
-   The origin server requires higher performance to withstand high-concurrent downloads or download spikes. The bandwidth cost of the origin server is high.

## On-demand audio and video streaming

Alibaba Cloud CDN distributes and accelerates the delivery of audio and video content on websites and applications, such as film and television websites, online education websites, news websites, and short video websites.

This feature addresses the following issues:

-   Errors or stalling issues that occur when users request video content.
-   Your website or application is vulnerable to hijacking or unauthorized downloads of video content. The copyright of the video content requires protection.
-   The origin server requires higher performance to withstand high-concurrent downloads or download spikes. The bandwidth cost of the origin server is high.

Apart from the preceding features, if you want an all-in-one service that can upload, transcode, store, and distribute audio or video content at the same time, you can use ApsaraVideo VOD. For more information, see [What is ApsaraVideo VOD?](/intl.en-US/Introduction/What is ApsaraVideo VOD?.md)

