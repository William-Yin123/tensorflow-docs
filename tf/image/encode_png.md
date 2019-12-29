<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.image.encode_png" />
<meta itemprop="path" content="Stable" />
</div>

# tf.image.encode_png

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/image_ops_impl.py">View source</a>



PNG-encode an image.

``` python
tf.image.encode_png(
    image,
    compression=-1,
    name=None
)
```



<!-- Placeholder for "Used in" -->

`image` is a 3-D uint8 or uint16 Tensor of shape `[height, width, channels]`
where `channels` is:

*   1: for grayscale.
*   2: for grayscale + alpha.
*   3: for RGB.
*   4: for RGBA.

The ZLIB compression level, `compression`, can be -1 for the PNG-encoder
default or a value from 0 to 9.  9 is the highest compression level,
generating the smallest output, but is slower.

#### Args:


* <b>`image`</b>: A `Tensor`. Must be one of the following types: `uint8`, `uint16`.
  3-D with shape `[height, width, channels]`.
* <b>`compression`</b>: An optional `int`. Defaults to `-1`. Compression level.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `string`.


## Compat aliases

* `tf.compat.v1.image.encode_png`
* `tf.compat.v2.image.encode_png`

