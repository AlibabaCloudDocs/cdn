# Overview

Alibaba Cloud Content Delivery Network \(CDN\) supports the image editing feature, which edits and distributes images on CDN nodes. This feature simplifies the back-to-origin process, reduces the number of requests that are redirected to origin servers, and reduces loads on origin servers. Image editing allows you to resize images, crop images, add watermarks to images, and perform other operations on images based on business requirements. The image editing feature of Alibaba Cloud CDN and the Image Processing \(IMG\) feature of Object Storage Service \(OSS\) are two separate features.

**Note:** Image editing is a paid service. It is currently free of charge until further notice.

## Scenarios

You must add a domain name to Alibaba Cloud CDN before you can enable image editing. After image editing is enabled, images are edited and cached on CDN nodes. This reduces loads on origin servers.

The following table describes some of the applicable scenarios.

|Scenario|Feature|
|--------|-------|
|**E-commerce platforms**|-   Efficiently edits different styles of image to be displayed on different terminals.
-   Compresses images and their comments, changes image quality, and reduces data transfer.
-   Adds watermarks to images to protect your copyright and promote your brand. |
|**Social media**|-   Edits images to be posted on social media based on user requirements.
-   Adds watermarks to images to protect digital assets. |
|**Online education**|-   Edits images to be used in online education materials based on user requirements.
-   Allows you to choose the type of compression that you want to enable based on business requirements. This helps you balance compression with image quality. |
|**Websites that provide design resources**|-   Efficiently edits different styles of image to be displayed on different terminals.
-   Allows you to compress images without compromising the image quality to accelerate image delivery. This allows websites to provide high-definition images. |

## Benefits

Image editing offers the following benefits:

-   **Accelerated delivery**

    After a base image is cached on CDN nodes, the CDN nodes directly resize the image based on requests and return resized images to clients. This improves delivery efficiency.

-   **Reduced loads on origin servers**

    If images are edited and stored on origin servers, the images consume storage and computing resources of the origin servers and increase the maintenance cost of the origin servers. This feature allows images to be edited and cached on CDN nodes. Therefore, loads on origin servers are reduced.

-   **Improved refresh and prefetch efficiency**

    After a base image expires, all images edited based on the base image are expired and become unavailable. To address this issue, images are edited and cached on CDN nodes. This solution reduces the frequency of refresh and prefetch tasks and the amount of bandwidth resources consumed by requests that are redirected to origin servers. Newly edited mages are cached on CDN nodes to ensure the availability of base images and edited images.

-   **Image editing on CDN nodes**

    This feature can recognize image editing parameters and edit images to adapt to different browsers and clients. It helps you meet the requirements of different users.


## Limits

When you use image editing, take note of the following limits:

-   Limits on base images
    -   Only the following image formats are supported: JPEG, PNG, WebP, BMP, GIF, TIFF, and JPEG 2000.
    -   The size of a base image cannot exceed 10 MB.
    -   The total pixels of a base image cannot exceed 16,777,216 pixels.
-   Limits on edited images
    -   The total pixels of an edited image cannot exceed 16,777,216 pixels.
    -   If you want to convert an edited image to the WebP format, the total pixels of the image cannot exceed 16,777,216 pixels. The width or height cannot exceed 16,384 pixels.

## Related topics

-   For more information about how to enable image editing, see [Enable image editing](/intl.en-US/Domain Management/Performance optimization/Image editing/Enable image editing.md).
-   For more information about how to configure image editing, see [Configure image editing](/intl.en-US/Domain Management/Performance optimization/Image editing/Enable image editing.md).

