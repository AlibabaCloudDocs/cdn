# Rotate images

Alibaba Cloud Content Delivery Network \(CDN\) supports automatic and manual image rotation. You can use this feature to enable Alibaba Cloud CDN to automatically rotate images or to manually rotate images to a specified orientation. This topic describes how to rotate images and provides examples of how to rotate images.

## Automatic rotation

Images taken by some cameras may be displayed in a specific orientation. You can specify whether to automatically rotate these images to a proper orientation.

Set the action to `auto-orient`.

Example: `image_process=auto-orient`.

## Manual rotation

Images can be rotated to a specific angle clockwise. Supported angles are 90°, 180°, and 270°.

Set the action to `rotate`.

Example: `image_process=rotate,180`.

