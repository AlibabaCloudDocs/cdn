# Change the color of an image

The color of an image includes the brightness, contrast, and sharpness. Alibaba Cloud Content Delivery Network \(CDN\) allows you to change the brightness, contrast, and sharpness of images on CDN nodes. This topic describes how to change the color of images and provides examples.

**Note:** This feature is **free of charge** during the public preview. After official release, it charges fees. For more information, see the product updates.

## Parameters

Set the following parameters:

-   `bright`: specifies the brightness of images.
-   `contrast`: specifies the contrast of images.
-   `sharpen`: specifies the sharpness of images.

## Examples

The following table describes the parameters.

|Parameter|Description|Example|
|---------|-----------|-------|
|brightness|Specifies the brightness of images. Valid values: -100 to 100.|```
image_process=bright,50
``` |
|contrast|Specifies the contrast of images. Valid values: -100 to 100.|```
image_process=contrast,50
``` |
|sharpen|Specifies the sharpness of images. Valid values: 50 to 399. We recommend that you use the following values: 50, 100, 150, 200, 250, and 300.|```
image_process=sharpen,100
``` |

