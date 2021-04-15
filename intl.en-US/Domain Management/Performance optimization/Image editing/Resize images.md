# Resize images

Alibaba Cloud Content Delivery Network \(CDN\) allows you to resize images. This topic describes how to resize images and provides examples.

**Note:** Image editing is a paid service. It is currently free of charge until further notice.

## Parameters

Set the action to `resize`.

The following table describes the parameters.

**Note:** If one of the preceding parameters is set to a negative value, the image remains in its original size.

|Parameter|Description|Valid value|
|---------|-----------|-----------|
|w|Specifies the width to which the image is to be resized.|The default value is 0. The total pixels of the image cannot exceed 16,777,216 pixels.|
|h|Specifies the height to which the image is to be resized.|
|l|Specifies the length of the longer side to which the image is to be resized.|
|s|Specifies the length of the shorter side to which the image is to be resized.|
|fw and fh|Specifies the width and height to which the image is to be resized.|
|p|Specifies that the image is resized based on a specific aspect ratio of the original image size.|\[0,100\]|

## Examples

The following table describes how to resize images.

|Feature|Description|Example|
|-------|-----------|-------|
|Based on a specific aspect ratio|Resize an image based on a specific aspect ratio of the original image size.|```
image_process=resize,p_80
``` |
|Based on conditions|Resize an image only when the image is equal to or larger than 1,024,000 bytes. Unit: bytes. **Note:** The threshold of 1,024,000 bytes is used as an example. You can set the threshold based on your business requirements.

|```
image_process=resize,l_200/threshold,1024000
``` |
|Based on the longer side|Resize an image based on the specified length of the longer side.|```
image_process=resize,l_200
``` |
|Based on the shorter side.|Resize an image based on the specified length of the shorter side.|```
image_process=resize,s_200
``` |
|Based on the width|Resize an image based on the specified width.|```
image_process=resize,w_200
``` |
|Based on the height|Resize an image based on the specified height.|```
image_process=resize,h_200
``` |
|Based on the specified height and width|Resize an image based on the specified width and height.|```
image_process=resize,fw_200,fh_200
``` |

