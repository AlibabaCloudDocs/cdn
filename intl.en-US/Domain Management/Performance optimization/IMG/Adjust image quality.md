# Adjust image quality

You can adjust the quality of an image by compressing the image, changing the absolute quality value, and changing the quality coefficient. Alibaba Cloud Content Delivery Network \(CDN\) allows you to compress images stored on CDN nodes without changing the image format.

## Compress images

This feature reduces the size of all images under a domain name without changing the resolution, format, or quality of the images.

**Note:** To enable this feature, [submit ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex).

## Change the absolute quality value

Set the action to `quality`. The absolute quality value is specified by the Q parameter.

**Note:**

-   The absolute quality value must be within 0 and 100, and be a multiple of 5. Other values are not supported.
-   A greater quality value represents a higher quality and a higher clarity.

Image quality can be represented by an absolute value. You cannot adjust the image quality to a higher value. For example, if you set `image_process=quality,Q_90`, the attempt to adjust the image quality from 80 to 90 fails and the image quality remains at 80.

## Change the quality coefficient

Set the action to `quality`. The quality coefficient is specified by the q parameter.

**Note:**

-   The absolute quality value must be within 0 and 100, and be a multiple of 5. Other values are not supported.
-   A greater quality value represents a higher quality and a higher clarity.

Image quality can be adjusted based on the original quality and a quality coefficient. For example, if you set `image_process=quality,q_90` to adjust an image whose quality is 80, the image quality is adjusted to 72.

