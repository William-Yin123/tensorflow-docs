<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.as_bytes" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.as_bytes

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/util/compat.py">View source</a>



Converts `bytearray`, `bytes`, or unicode python input types to `bytes`.

``` python
tf.compat.as_bytes(
    bytes_or_text,
    encoding='utf-8'
)
```



<!-- Placeholder for "Used in" -->

Uses utf-8 encoding for text by default.

#### Args:


* <b>`bytes_or_text`</b>: A `bytearray`, `bytes`, `str`, or `unicode` object.
* <b>`encoding`</b>: A string indicating the charset for encoding unicode.


#### Returns:

A `bytes` object.



#### Raises:


* <b>`TypeError`</b>: If `bytes_or_text` is not a binary or unicode string.

## Compat aliases

* `tf.compat.v1.compat.as_bytes`
* `tf.compat.v2.compat.as_bytes`

