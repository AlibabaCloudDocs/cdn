# Resize images

Alibaba Cloud Content Delivery Network \(CDN\) allows you to resize images. This topic describes how to resize images and provides examples of how to resize images.

**Note:**

-   This feature is in private preview. To participate in the private preview, [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex).
-   This feature is **free of charge** during the private preview. After it is officially released, it charges fees. For more information, see the product updates.

## Parameters

Set the action to `resize`.

The following table describes the parameters.

|Parameter|Description|Valid value|
|---------|-----------|-----------|
|w|Specifies the width to which the image is to be resized.|The default value is 0. Unit: pixels. Both the width and height can be at most 4,096 pixels.|
|h|Specifies the height to which the image is to be resized.|
|l|Specifies the length of the longer side to which the image is to be resized.|
|s|Specifies the length of the shorter side to which the image is to be resized.|
|fw and fh|Specifies the width and height to which the image is to be resized.|
|p|Specifies that the image is resized based on a specific aspect ratio of the original image size.|\[0,100\]|

## Features and examples

The following table provides examples of resizing images.

**Note:** If any of the preceding parameters is set to a negative value, the image remains in its original size.

|Feature|Description|Example|
|-------|-----------|-------|
|Based on a specific aspect ratio|Resize an image based on a specific aspect ratio of the original image size.|image\_process=resize,p\_80|
|Based on conditions|Resize an image only when the image is equal to or larger than 1,024,000 bytes. Unit: bytes.**Note:** The threshold 1,024,000 bytes is used as an example. You can set the threshold based on your business requirements.

|image\_process=resize,l\_200/threshold\_1024000|
|Based on the longer side|Resize an image based on the specified length of the longer side.|image\_process=resize,l\_200|
|Based on the shorter side.|Resize an image based on the specified length of the shorter side.|image\_process=resize,s\_200|
|Based on the width|Resize an image based on the specified width.|image\_process=resize,w\_200|
|Based on the height|Resize an image based on the specified height.|image\_process=resize,h\_200|
|Based on the specified height and width|Resize an image based on the specified width and height.|image\_process=resize,fw\_200,fh\_200|

