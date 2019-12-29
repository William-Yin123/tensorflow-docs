<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.as_text" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.as_text

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/util/compat.py">View source</a>



Converts any string-like python input types to unicode.

**Aliases**: `tf.compat.as_str`

``` python
tf.compat.as_text(
    bytes_or_text,
    encoding='utf-8'
)
```



<!-- Placeholder for "Used in" -->

Returns the input as a unicode string. Uses utf-8 encoding for text
by default.

#### Args:


* <b>`bytes_or_text`</b>: A `bytes`, `str`, or `unicode` object.
* <b>`encoding`</b>: A string indicating the charset for decoding unicode.


#### Returns:

A `unicode` (Python 2) or `str` (Python 3) object.



#### Raises:


* <b>`TypeError`</b>: If `bytes_or_text` is not a binary or unicode string.

## Compat aliases

* `tf.compat.v1.compat.as_str`
* `tf.compat.v1.compat.as_text`
* `tf.compat.v2.compat.as_str`
* `tf.compat.v2.compat.as_text`

