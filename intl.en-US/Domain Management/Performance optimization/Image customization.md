# Image customization

Alibaba Cloud Content Delivery Network \(CDN\) allows you to customize images. This topic describes how to customize images.

## Feature description

You can specify conditions to customize images.

This feature is in private preview. To apply for the use of this feature,[submit a ticket](https://selfservice.console.aliyun.com/ticket/createIndex).

## Basic settings

Alibaba Cloud CDN allows you to customize images on CDN nodes. You can pass parameters to the `image_process` object to specify how you want to customize the images.

You can pass multiple parameters to the object. Separate multiple parameters with forward slashes \(/\).

Format: `image_process=action1,param_value1/action2,param_value2`.

Example: `image_process=resize,l_200/quality,q_90/format,webp`.

The following settings are supported:

-   image\_transform\_enable: Specify whether to enable image customization. Valid values: on and off.
-   image\_transform\_filetype: Specify the image formats. Both the original format and desired format must be supported by image customization. Valid values: jpg, png, and webp.

## Resize images

Set the action to `resize`.

-   Specify the longer side to resize images based on a specific aspect ratio. Example: `image_process=resize,l_200`.
-   Specify the shorter side to resize images based on a specific aspect ratio. Example: `image_process=resize,s_200`.
-   Specify the width to resize images based on a specific aspect ratio. Example: `image_process=resize,w_200`.
-   Specify the height to resize images based on a specific aspect ratio. Example: `image_process=resize,h_200`.
-   Specify both the width and height to resize images. Example: `image_process=resize,fw_200,fh_200`.

If the value is set to a negative number, images remain at their original sizes.

## Crop images

Set the action to `crop`.

-   You can specify the x coordinate, y coordinate, width, and height to crop an image. The x and y coordinates specify the lower-left corner of an image. The width and height specify the size to which you want to crop the image. Example: `image_process=crop,x_10,y_10,w_400,h_200`.
-   You can specify the width and height to crop equally on all four sides at a time. Example: `image_process=crop,mid,w_400,h_200`.

If the value is set to a negative number, images remain at their original sizes.

## Adjust image quality

Set the action to `quality`.

-   Image quality can be represented by an absolute value. You cannot adjust the image quality to a higher value. For example, if you set `image_process=quality,Q_90`, the attempt to adjust the image quality from 80 to 90 fails and the image quality remains at 80.
-   Image quality can be adjusted based on the original quality and a quality coefficient. For example, if you set `image_process=quality,q_90` to adjust an image whose quality is 80, the image quality is adjusted to 72.

Valid range of the quality coefficient: 0 < quality < 100. The coefficient must be a positive multiple of 5 \(quality % 5 == 0\). Other values are not supported.

## Sharpen images

Set the action to `sharpen`.

Images sharpening increases the apparent sharpness of an image. Valid values are 50, 100, 150, 200, 250, and 300.

Example: `image_process=sharpen,100`.

## Rotate images

Set the action to `rotate`.

Images can be rotated to a specific angle clockwise. Supported angles are 90, 180, and 270. Example: `image_process=rotate,180`.

## Automatically orient images

Set the action to `auto-orient`.

Images taken by some cameras may be displayed in a specific orientation. You can specify whether to automatically rotate these images to a proper orientation. Example: `image_process=auto-orient`.

## Convert image formats

Set the action to `format`.

You can convert images to a specific format. Example: `image_process=format,webp`.

## Compress images

This feature is enabled after your application for the image customization feature is approved. This feature reduces the size of all images under a domain name without changing the resolution, format, or quality of the images.

## Automatically convert images to WebP

This feature is enabled after your application for the image customization feature is approved. Alibaba Cloud CDN determines whether to convert images in a response to the WebP format based on the Accept parameter in the request header. If `image/webp` is included in the request header, images in the response are converted to the WebP format. Example: `Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9`.

