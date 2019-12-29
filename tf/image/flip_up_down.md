<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.image.flip_up_down" />
<meta itemprop="path" content="Stable" />
</div>

# tf.image.flip_up_down

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/image_ops_impl.py">View source</a>



Flip an image vertically (upside down).

``` python
tf.image.flip_up_down(image)
```



<!-- Placeholder for "Used in" -->

Outputs the contents of `image` flipped along the height dimension.

See also `reverse()`.

#### Args:


* <b>`image`</b>: 4-D Tensor of shape `[batch, height, width, channels]` or 3-D Tensor
  of shape `[height, width, channels]`.


#### Returns:

A `Tensor` of the same type and shape as `image`.



#### Raises:


* <b>`ValueError`</b>: if the shape of `image` not supported.

## Compat aliases

* `tf.compat.v1.image.flip_up_down`
* `tf.compat.v2.image.flip_up_down`

