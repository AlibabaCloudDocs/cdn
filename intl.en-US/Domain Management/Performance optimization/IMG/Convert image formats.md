# Convert image formats

Alibaba Cloud Content Delivery Network \(CDN\) can automatically convert image formats to WebP or convert image formats to a specified format. You can convert images stored on CDN nodes to specified formats. This topic describes how to convert image formats and provides examples of this feature.

## Automatically convert images to WebP

Alibaba Cloud CDN determines whether to convert images in a response to the WebP format based on the Accept header in the request. If `image/webp` is included in the request header, images in the response are converted to the WebP format.

Example: `Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9`.

**Note:** To enable this feature, you must [submit ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex).

## Convert images to specified formats

**Parameters**

Set the action to `format`. The following table describes the parameters.

|Supported format|Description|
|----------------|-----------|
|JPEG|Converts base images to the JPG or JPEG format.|
|PNG|Converts base images to the PNG format.|
|WEBP|Converts base images to the WebP format.|
|BMP|Converts base images to the BMP format.|
|GIF|Converts base images to the TIFF format.**Note:** GIF images are animated. If you convert a GIF image to another format, the image is no longer animated and becomes static. |
|TIFF|Converts base images to the TIFF format.|
|JPEG 2000|Converts base images to the JPEG 2000 format. The suffix of the names of the JPEG 2000 images is JP2.|

**Example**

Example: `image_process=format,bmp`.

