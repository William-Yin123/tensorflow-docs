<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.image.crop_and_resize" />
<meta itemprop="path" content="Stable" />
</div>

# tf.image.crop_and_resize

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/image_ops_impl.py">View source</a>



Extracts crops from the input image tensor and resizes them.

``` python
tf.image.crop_and_resize(
    image,
    boxes,
    box_indices,
    crop_size,
    method='bilinear',
    extrapolation_value=0,
    name=None
)
```



<!-- Placeholder for "Used in" -->

Extracts crops from the input image tensor and resizes them using bilinear
sampling or nearest neighbor sampling (possibly with aspect ratio change) to a
common output size specified by `crop_size`. This is more general than the
`crop_to_bounding_box` op which extracts a fixed size slice from the input
image and does not allow resizing or aspect ratio change.

Returns a tensor with `crops` from the input `image` at positions defined at
the bounding box locations in `boxes`. The cropped boxes are all resized (with
bilinear or nearest neighbor interpolation) to a fixed
`size = [crop_height, crop_width]`. The result is a 4-D tensor
`[num_boxes, crop_height, crop_width, depth]`. The resizing is corner aligned.
In particular, if `boxes = [[0, 0, 1, 1]]`, the method will give identical
results to using <a href="../../tf/compat/v1/image/resize_bilinear.md"><code>tf.compat.v1.image.resize_bilinear()</code></a> or
<a href="../../tf/compat/v1/image/resize_nearest_neighbor.md"><code>tf.compat.v1.image.resize_nearest_neighbor()</code></a>(depends on the `method`
argument) with
`align_corners=True`.

#### Args:


* <b>`image`</b>: A 4-D tensor of shape `[batch, image_height, image_width, depth]`.
  Both `image_height` and `image_width` need to be positive.
* <b>`boxes`</b>: A 2-D tensor of shape `[num_boxes, 4]`. The `i`-th row of the tensor
  specifies the coordinates of a box in the `box_ind[i]` image and is
  specified in normalized coordinates `[y1, x1, y2, x2]`. A normalized
  coordinate value of `y` is mapped to the image coordinate at `y *
  (image_height - 1)`, so as the `[0, 1]` interval of normalized image
  height is mapped to `[0, image_height - 1]` in image height coordinates.
  We do allow `y1` > `y2`, in which case the sampled crop is an up-down
  flipped version of the original image. The width dimension is treated
  similarly. Normalized coordinates outside the `[0, 1]` range are allowed,
  in which case we use `extrapolation_value` to extrapolate the input image
  values.
* <b>`box_indices`</b>: A 1-D tensor of shape `[num_boxes]` with int32 values in `[0,
  batch)`. The value of `box_ind[i]` specifies the image that the `i`-th box
  refers to.
* <b>`crop_size`</b>: A 1-D tensor of 2 elements, `size = [crop_height, crop_width]`.
  All cropped image patches are resized to this size. The aspect ratio of
  the image content is not preserved. Both `crop_height` and `crop_width`
  need to be positive.
* <b>`method`</b>: An optional string specifying the sampling method for resizing. It
  can be either `"bilinear"` or `"nearest"` and default to `"bilinear"`.
  Currently two sampling methods are supported: Bilinear and Nearest
    Neighbor.
* <b>`extrapolation_value`</b>: An optional `float`. Defaults to `0`. Value used for
  extrapolation, when applicable.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A 4-D tensor of shape `[num_boxes, crop_height, crop_width, depth]`.



#### Example:



```python
import tensorflow as tf
BATCH_SIZE = 1
NUM_BOXES = 5
IMAGE_HEIGHT = 256
IMAGE_WIDTH = 256
CHANNELS = 3
CROP_SIZE = (24, 24)

image = tf.random.normal(shape=(BATCH_SIZE, IMAGE_HEIGHT, IMAGE_WIDTH,
CHANNELS) )
boxes = tf.random.uniform(shape=(NUM_BOXES, 4))
box_indices = tf.random.uniform(shape=(NUM_BOXES,), minval=0,
maxval=BATCH_SIZE, dtype=tf.int32)
output = tf.image.crop_and_resize(image, boxes, box_indices, CROP_SIZE)
output.shape  #=> (5, 24, 24, 3)
```

## Compat aliases

* `tf.compat.v2.image.crop_and_resize`

