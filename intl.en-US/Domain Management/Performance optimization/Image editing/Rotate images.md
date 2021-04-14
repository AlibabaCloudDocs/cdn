# Rotate images

Alibaba Cloud Content Delivery Network \(CDN\) supports automatic and manual image rotation. You can use this feature to enable Alibaba Cloud CDN to automatically rotate images or to manually rotate images to a specified orientation. This topic describes how to rotate images and provides examples.

**Note:** This feature is **free of charge** during the public preview. After official release, it charges fees. For more information, see the product updates.

## Automatic rotation

Images taken by some cameras carry the orientation parameter and are displayed in a specific orientation. You can enable this feature to automatically rotate these images to a proper orientation. For more information, see [Enable image editing]().

**Note:** After you enable automatic conversion to WebP, the cache hit ratio decreases. It automatically increases after a short period of time. Do not enable this feature during peak hours.

Set the action to `auto-orient`.

Examples

```
image_process=auto-orient
```

## Manual rotation

Images can be rotated to a specific angle clockwise. Supported angles are 90°, 180°, and 270°.

Set the action to `rotate`.

Examples

```
image_process=rotate,180
```

