<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.image.adjust_jpeg_quality" />
<meta itemprop="path" content="Stable" />
</div>

# tf.image.adjust_jpeg_quality

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/image_ops_impl.py">View source</a>



Adjust jpeg encoding quality of an image.

``` python
tf.image.adjust_jpeg_quality(
    image,
    jpeg_quality,
    name=None
)
```



<!-- Placeholder for "Used in" -->

This is a convenience method that converts an image to uint8 representation,
encodes it to jpeg with `jpeg_quality`, decodes it, and then converts back
to the original data type.

`jpeg_quality` must be in the interval `[0, 100]`.

#### Args:


* <b>`image`</b>: 3D image. The size of the last dimension must be None, 1 or 3.
* <b>`jpeg_quality`</b>: Python int or Tensor of type int32. jpeg encoding quality.
* <b>`name`</b>: A name for this operation (optional).


#### Returns:

Adjusted image, same shape and DType as `image`.



#### Usage Example:

```python
>> import tensorflow as tf
>> x = tf.random.normal(shape=(256, 256, 3))
>> tf.image.adjust_jpeg_quality(x, 75)
```


#### Raises:


* <b>`InvalidArgumentError`</b>: quality must be in [0,100]
* <b>`InvalidArgumentError`</b>: image must have 1 or 3 channels

## Compat aliases

* `tf.compat.v1.image.adjust_jpeg_quality`
* `tf.compat.v2.image.adjust_jpeg_quality`

