# Convert image formats

Alibaba Cloud Content Delivery Network \(CDN\) can automatically convert images to the WebP format. You can also convert images on CDN nodes to specified formats. This topic describes how to convert image formats and provides examples.

**Note:** Image editing is a paid service. It is currently free of charge until further notice.

## Automatically convert images to WebP

WebP supports both lossy compression and lossless compression. Alibaba Cloud CDN can automatically convert images to the WebP format. After you enable automatic conversion to WebP, Alibaba Cloud CDN determines whether to convert images to the WebP format based on the Accept header in requests. If `image/webp` is included in the Accept header, images in the response are converted to the WebP format. For more information, see [Enable image editing](/intl.en-US/Domain Management/Performance optimization/Image editing/Enable image editing.md).

**Note:** After you enable automatic conversion to WebP, the cache hit ratio decreases. It automatically increases after a short period of time. Do not enable this feature during peak hours.

**Examples**

The Accept header used in this topic is for reference only. The actual Accept header shall prevail. In the following example, `image/webp` is included in the Accept header. This indicates that Alibaba Cloud CDN automatically converts images to the WebP format.

```
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
```

## Convert images to specified formats

**Parameters**

Set the action to `format`.

The following table describes the formats to which images can be converted.

|Supported format|Description|
|----------------|-----------|
|JPEG|Converts base images to the JPG or JPEG format.|
|PNG|Converts base images to the PNG format.|
|WEBP|Converts base images to the WebP format.|
|BMP|Converts base images to the BMP format.|
|GIF|Converts base images to the TIFF format. **Note:** GIF images are animated. If you convert a GIF image to another format, the image is no longer animated and becomes static. |
|TIFF|Converts base images to the TIFF format.|
|JPEG 2000|Converts base images to the JPEG 2000 format. The suffix of the names of JPEG 2000 images is JP2.|

**Examples**

```
image_process=format,bmp
```

