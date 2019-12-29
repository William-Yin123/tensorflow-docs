<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.extract_image_patches" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.extract_image_patches

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/array_ops.py">View source</a>



Extract `patches` from `images` and put them in the "depth" output dimension.

``` python
tf.compat.v1.extract_image_patches(
    images,
    ksizes=None,
    strides=None,
    rates=None,
    padding=None,
    name=None,
    sizes=None
)
```



<!-- Placeholder for "Used in" -->


#### Args:


* <b>`images`</b>: A `Tensor`. Must be one of the following types: `float32`, `float64`, `int32`, `uint8`, `int16`, `int8`, `int64`, `bfloat16`, `uint16`, `half`, `uint32`, `uint64`.
  4-D Tensor with shape `[batch, in_rows, in_cols, depth]`.
* <b>`ksizes`</b>: A list of `ints` that has length `>= 4`.
  The size of the sliding window for each dimension of `images`.
* <b>`strides`</b>: A list of `ints` that has length `>= 4`.
  How far the centers of two consecutive patches are in
  the images. Must be: `[1, stride_rows, stride_cols, 1]`.
* <b>`rates`</b>: A list of `ints` that has length `>= 4`.
  Must be: `[1, rate_rows, rate_cols, 1]`. This is the
  input stride, specifying how far two consecutive patch samples are in the
  input. Equivalent to extracting patches with
  `patch_sizes_eff = patch_sizes + (patch_sizes - 1) * (rates - 1)`, followed by
  subsampling them spatially by a factor of `rates`. This is equivalent to
  `rate` in dilated (a.k.a. Atrous) convolutions.
* <b>`padding`</b>: A `string` from: `"SAME", "VALID"`.
  The type of padding algorithm to use.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `images`.


## Compat aliases

* `tf.compat.v1.image.extract_image_patches`

