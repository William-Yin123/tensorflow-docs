<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.strings.length" />
<meta itemprop="path" content="Stable" />
</div>

# tf.strings.length

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/string_ops.py">View source</a>



String lengths of `input`.

``` python
tf.strings.length(
    input,
    unit='BYTE',
    name=None
)
```



<!-- Placeholder for "Used in" -->

Computes the length of each string given in the input tensor.

```
>>> strings = tf.constant(['Hello','TensorFlow', '\U0001F642'])
>>> tf.strings.length(strings).numpy() # default counts bytes
array([ 5, 10, 4], dtype=int32)
>>> tf.strings.length(strings, unit="UTF8_CHAR").numpy()
array([ 5, 10, 1], dtype=int32)
```

#### Args:


* <b>`input`</b>: A `Tensor` of type `string`.
  The strings for which to compute the length for each element.
* <b>`unit`</b>: An optional `string` from: `"BYTE", "UTF8_CHAR"`. Defaults to `"BYTE"`.
  The unit that is counted to compute string length.  One of: `"BYTE"` (for
  the number of bytes in each string) or `"UTF8_CHAR"` (for the number of UTF-8
  encoded Unicode code points in each string).  Results are undefined
  if `unit=UTF8_CHAR` and the `input` strings do not contain structurally
  valid UTF-8.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `int32`.


## Compat aliases

* `tf.compat.v2.strings.length`

