# Change image quality

You can adjust the quality of an image by compressing the image, changing the absolute quality value, and changing the quality coefficient. Alibaba Cloud Content Delivery Network \(CDN\) allows you to compress images on CDN nodes without changing the image format.

**Note:** Image editing is a paid service. It is currently free of charge until further notice.

## Compress images

This feature reduces the size of all images that belong to a domain name without changing the resolution, format, or quality of the images. For more information, see [Enable image editing](/intl.en-US/Domain Management/Performance optimization/Image editing/Enable image editing.md).

## Change image quality

**Parameters**

Set the action to `quality`.

The following table describes the parameters.

|Parameter|Description|Valid value|
|---------|-----------|-----------|
|Q|Specifies an absolute quality value. Image quality can be represented by an absolute value. You cannot adjust the image quality to a higher value.|0<Q<100. The value must be a multiple of 5. Other values are not supported.

**Note:** A greater quality value represents a higher quality and a higher clarity. We recommend that you set Q to 95. |
|q|Specifies a quality coefficient. Image quality can be adjusted based on the original quality and a quality coefficient.|0<q<100. The value must be a multiple of 5. Other values are not supported.

**Note:** A greater quality value represents a higher quality and a higher clarity. We recommend that you set Q to 95. |

**Examples**

-   Specify an absolute quality value: If you set `image_process=quality,Q_90` and the current quality is 80, the attempt to adjust the image quality from 80 to 90 fails. The image quality remains at 80.
-   Specify a quality coefficient: If you set `image_process=quality,q_90` to adjust an image whose current quality is 80, the image quality is adjusted to 72.

