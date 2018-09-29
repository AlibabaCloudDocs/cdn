# Scenarios {#concept_o5j_x3g_tdb .concept}

## To accelerate the distribution of resources for websites, or applications, {#section_smn_pjg_tdb .section}

with a large volume of static resources. We recommend that you separate the dynamic and static contents. You can use Alibaba Cloud CDN to accelerate the static content, and use cloud server ECS to accelerate dynamic content. For large volumes of static resources such as image, css, and small js files, we recommend that you store them on OSS. This can accelerate content download speeds and make it easy to perform distribution for images, videos, and other media content.


## Acceleration of on-demand audio and video/large file downloads and distribution {#section_umn_pjg_tdb .section}

Alibaba Cloud CDN supports the downloading and distributing of various types of files. It also supports the acceleration of online on-demand streaming services, for example, MP4 and FLV videos, or scenarios where the average size of a single file is greater than 20 MB. The primary service scenarios are on-demand video/audio and large file downloads \(for example, installation packages\). You can combine CDN with OSS to increase origin retrieval speeds to reduce origin retrieval bandwidth cost by 2/3.


## Live acceleration {#section_wmn_pjg_tdb .section}

Alibaba Cloud [ApsaraVideo Live](https://www.alibabacloud.com/zh/product/apsaravideo-for-live?spm=a2796.7919406.1097650.dznavproductsj1.62616ecf7Cjj4c) service has been released on-line separately. ApsaraVideo Live is an audio-video platform based on the latest accessible content, CDN network and largely distributed real-time transcoding technology. It offers high-definition, live audio-video feed services that are fluent and easily accessible with low latency rate and are high in concurrency. It supports multiple live scenarios, with all-round data statistics and a wide array of perspective analysis. It also provides multiple lives features, such as recording playback, real-time covers, real-time transcoding, and connected-microphone multiplexing.


## Mobile application acceleration {#section_ymn_pjg_tdb .section}

For the distribution of mobile app update files \(APK files\), CDN delivers optimized and accelerated distribution of in-app images, pages, short videos, UGC, and other media content. The http DNS service prevents DNS hijacking and retrieves precise DNS resolution results in real time, effectively reducing user access time and improving user experience.

