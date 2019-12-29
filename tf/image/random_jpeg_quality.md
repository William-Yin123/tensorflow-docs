<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.image.random_jpeg_quality" />
<meta itemprop="path" content="Stable" />
</div>

# tf.image.random_jpeg_quality

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/image_ops_impl.py">View source</a>



Randomly changes jpeg encoding quality for inducing jpeg noise.

``` python
tf.image.random_jpeg_quality(
    image,
    min_jpeg_quality,
    max_jpeg_quality,
    seed=None
)
```



<!-- Placeholder for "Used in" -->

`min_jpeg_quality` must be in the interval `[0, 100]` and less than
`max_jpeg_quality`.
`max_jpeg_quality` must be in the interval `[0, 100]`.

#### Args:


* <b>`image`</b>: 3D image. Size of the last dimension must be 1 or 3.
* <b>`min_jpeg_quality`</b>: Minimum jpeg encoding quality to use.
* <b>`max_jpeg_quality`</b>: Maximum jpeg encoding quality to use.
* <b>`seed`</b>: An operation-specific seed. It will be used in conjunction with the
  graph-level seed to determine the real seeds that will be used in this
  operation. Please see the documentation of set_random_seed for its
  interaction with the graph-level random seed.


#### Returns:

Adjusted image(s), same shape and DType as `image`.



#### Raises:


* <b>`ValueError`</b>: if `min_jpeg_quality` or `max_jpeg_quality` is invalid.

## Compat aliases

* `tf.compat.v1.image.random_jpeg_quality`
* `tf.compat.v2.image.random_jpeg_quality`

