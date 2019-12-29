<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.io.decode_compressed" />
<meta itemprop="path" content="Stable" />
</div>

# tf.io.decode_compressed

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>



Decompress strings.

``` python
tf.io.decode_compressed(
    bytes,
    compression_type='',
    name=None
)
```



<!-- Placeholder for "Used in" -->

This op decompresses each element of the `bytes` input `Tensor`, which
is assumed to be compressed using the given `compression_type`.

The `output` is a string `Tensor` of the same shape as `bytes`,
each element containing the decompressed data from the corresponding
element in `bytes`.

#### Args:


* <b>`bytes`</b>: A `Tensor` of type `string`.
  A Tensor of string which is compressed.
* <b>`compression_type`</b>: An optional `string`. Defaults to `""`.
  A scalar containing either (i) the empty string (no
  compression), (ii) "ZLIB", or (iii) "GZIP".
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `string`.


## Compat aliases

* `tf.compat.v1.decode_compressed`
* `tf.compat.v1.io.decode_compressed`
* `tf.compat.v2.io.decode_compressed`

