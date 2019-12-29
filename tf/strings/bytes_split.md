<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.strings.bytes_split" />
<meta itemprop="path" content="Stable" />
</div>

# tf.strings.bytes_split

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/ragged/ragged_string_ops.py">View source</a>



Split string elements of `input` into bytes.

``` python
tf.strings.bytes_split(
    input,
    name=None
)
```



<!-- Placeholder for "Used in" -->


#### Examples:



```
>>> tf.strings.bytes_split('hello').numpy()
array([b'h', b'e', b'l', b'l', b'o'], dtype=object)
>>> tf.strings.bytes_split(['hello', '123'])
<tf.RaggedTensor [[b'h', b'e', b'l', b'l', b'o'], [b'1', b'2', b'3']]>
```

Note that this op splits strings into bytes, not unicode characters.  To
split strings into unicode characters, use <a href="../../tf/strings/unicode_split.md"><code>tf.strings.unicode_split</code></a>.

See also: <a href="../../tf/io/decode_raw.md"><code>tf.io.decode_raw</code></a>, <a href="../../tf/strings/split.md"><code>tf.strings.split</code></a>, <a href="../../tf/strings/unicode_split.md"><code>tf.strings.unicode_split</code></a>.

#### Args:


* <b>`input`</b>: A string `Tensor` or `RaggedTensor`: the strings to split.  Must
  have a statically known rank (`N`).
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `RaggedTensor` of rank `N+1`: the bytes that make up the source strings.


## Compat aliases

* `tf.compat.v1.strings.bytes_split`
* `tf.compat.v2.strings.bytes_split`

