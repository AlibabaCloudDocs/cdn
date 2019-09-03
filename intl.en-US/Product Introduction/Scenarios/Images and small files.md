# Images and small files {#concept_hrm_335_k2b .concept}

If your business requires the distribution of small static web pages or application files, such as images and files in such formats as HTML, Flash, CSS, and JavaScript, you can use CDN to accelerate the distribution of images and small files.

## Scenarios {#section_btt_zjr_z93 .section}

The Images and Small Files function is suitable for accelerating the distribution of large numbers of static resources on websites or applications, such as Web portals, e-commerce websites, news websites and apps, and gaming and other entertainment websites. You can separate static and dynamic content. We recommend that you use CDN to accelerate the distribution of static content, such as images and small CSS and JavaScript files.

The following figure shows typical application scenarios of image and small file distribution.

![Scenarios](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5101/15674927236000_en-US.jpg)

## Challenges that the Images and Small Files function can solve {#section_ybf_tck_l2b .section}

-   Websites respond slowly because they contain a large number of small files.
-   The access speeds and output quality of media files on websites differ across regions.
-   During high concurrency of promotions, origin servers are more likely to break down due to heavy traffic and services become unavailable.
-   Images cannot be compressed or optimized to fit the requirements of the destination client.

## Required Alibaba Cloud products and functions {#section_hxq_1dk_l2b .section}

The following table describes Alibaba Cloud products and functions required for the distribution of images and small files.

|Product or function|Description|
|-------------------|-----------|
|[Nodes](reseller.en-US/Product Introduction/Nodes.md#)|Alibaba Cloud CDN has more than 2,000 nodes in Mainland China, and over 500 nodes spread outside Mainland China, including China \(Hong Kong\), China \(Macao\), China \(Taiwan\), and overseas. The nodes provide up to 120 Tbit/s bandwidth, and serve all major carriers in China and six continents.|
|Intelligent scheduling|An advanced distributed system schedules traffic in all regions and responds to requests within milliseconds.|
|Elastic capacity expansion|Each node responds to and adjusts traffic to prevent origin servers from overloading. Using the pay-as-you-go billing method helps to increase cost-effectiveness of services in the cloud.|
|[Intelligent compression](../../../../reseller.en-US/Domain Management/Performance optimization/Configure intelligent compression.md#)|Images in various formats and resolutions are compressed to fit a wide range of clients, improving overall performance while maintaining the image quality.|

## Related operations {#section_kx9_s78_0hm .section}

Before adding an accelerated domain name in the CDN console and selecting a service type, you need to learn about the application scenarios of different service types. For more information about specific operations, see [Add a CDN domain](../../../../reseller.en-US/Quick Start/Add a CDN domain.md#).

