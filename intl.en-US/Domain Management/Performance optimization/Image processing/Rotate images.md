# Rotate images

Alibaba Cloud Content Delivery Network \(CDN\) supports automatic and manual image rotation. You can use this feature to enable Alibaba Cloud CDN to automatically rotate images or to manually rotate images to a specified orientation. This topic describes how to rotate images and provides examples of how to rotate images.

**Note:**

-   This feature is in private preview. To participate in the private preview, [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex).
-   This feature is **free of charge** during the private preview. After it is officially released, it charges fees. For more information, see the product updates.

## Automatic rotation

Images taken by some cameras may be displayed in a specific orientation. You can specify whether to automatically rotate these images to a proper orientation.

Set the action to `auto-orient`.

Example: `image_process=auto-orient`.

## Manual rotation

Images can be rotated to a specific angle clockwise. Supported angles are 90°, 180°, and 270°.

Set the action to `rotate`.

Example: `image_process=rotate,180`.

