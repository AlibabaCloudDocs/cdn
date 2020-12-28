# Image editing and benefits

Alibaba Cloud Content Delivery Network \(CDN\) allows you to edit images stored on CDN nodes. For example, you can add watermarks to images and convert image formats. This topic describes how to edit images and the benefits of this feature.

**Note:**

-   This feature is in private preview. To participate in the private preview, [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex).
-   This feature is **free of charge** during the private preview. After it is officially released, it charges fees. For more information, see the product updates.

## Benefits

-   Quick delivery: After the base image is cached on CDN nodes, the CDN nodes directly resize the image based on requests and return resized images to the requests. This improves delivery efficiency.
-   Reduced workloads on origin servers: If images are edited and stored on origin servers, the images consume storage and computing resources of origin servers and increase the maintenance cost of origin servers. This feature allows images to be edited and cached on CDN nodes. Therefore, workloads on origin servers are reduced.
-   Improved refresh and prefetch efficiency: After a base image expires, all images edited based on the base image are expired and become unavailable. To address this issue, images are edited and cached on CDN nodes. This solution reduces the frequency of refresh and prefetch tasks and the bandwidth usage of back-to-origin requests. Newly edited mages are cached on CDN nodes to ensure the availability of base images and edited images.
-   Image editing on CDN nodes: This feature can edit images based on user browsers and clients. It helps you meet the requirements of different users.

## Methods

Alibaba Cloud CDN allows you to edit images on CDN nodes. You can pass parameters to the `image_process` object to specify how you want to edit the images. You can pass multiple parameters such as `crop` and `rotate` to image\_process. Separate multiple parameters with forward slashes \(/\).

Format: `image_process=action1,param_value1/action2,param_value2`.

Example: `image_process=resize,l_200/quality,q_90/format,webp`.

## Parameters

You can pass one or more parameters to image\_process based on your business requirements. The following table describes the parameters that are used to edit images in different scenarios.

|Editing type|Parameter|Description|
|------------|---------|-----------|
|[Convert image formats](/intl.en-US/Domain Management/Performance optimization/Image processing/Convert image formats.md)|format|Converts image formats.|
|[Adjust image quality](/intl.en-US/Domain Management/Performance optimization/Image processing/Adjust image quality.md)|quality|Adjusts the quality of images.|
|[Crop images](/intl.en-US/Domain Management/Performance optimization/Image processing/Crop images.md)|crop|Crops images.|
|[Resize images](/intl.en-US/Domain Management/Performance optimization/Image processing/Resize images.md)|resize|Resizes images to a specified size.|
|[Rotate images](/intl.en-US/Domain Management/Performance optimization/Image processing/Rotate images.md)|-   auto-orient: automatically rotates images.
-   rotate: rotates images to a specified orientation.

|Automatically rotates images to a proper orientation or rotates images clockwise based on the specified angle.|
|[Change the color of an image](/intl.en-US/Domain Management/Performance optimization/Image processing/Change the color of an image.md)|-   bright: specifies the brightness of images.
-   contrast: specifies the contrast of images.
-   sharpen: specifies the sharpness of images.

|Adjusts the brightness, contrast, and sharpness of images.|
|[Manage image watermarks](/intl.en-US/Domain Management/Performance optimization/Image processing/Manage image watermarks.md)|watermark|Adds picture or text watermarks to images.|
|[Query image information](/intl.en-US/Domain Management/Performance optimization/Image processing/Query image information.md)|info|Queries image information, including the width, height, size, and format.|

