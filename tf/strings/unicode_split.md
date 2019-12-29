<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.strings.unicode_split" />
<meta itemprop="path" content="Stable" />
</div>

# tf.strings.unicode_split

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/ragged/ragged_string_ops.py">View source</a>



Splits each string in `input` into a sequence of Unicode code points.

``` python
tf.strings.unicode_split(
    input,
    input_encoding,
    errors='replace',
    replacement_char=65533,
    name=None
)
```



<!-- Placeholder for "Used in" -->

`result[i1...iN, j]` is the substring of `input[i1...iN]` that encodes its
`j`th character, when decoded using `input_encoding`.

#### Args:


* <b>`input`</b>: An `N` dimensional potentially ragged `string` tensor with shape
  `[D1...DN]`.  `N` must be statically known.
* <b>`input_encoding`</b>: String name for the unicode encoding that should be used to
  decode each string.
* <b>`errors`</b>: Specifies the response when an input string can't be converted
  using the indicated encoding. One of:
  * `'strict'`: Raise an exception for any illegal substrings.
  * `'replace'`: Replace illegal substrings with `replacement_char`.
  * `'ignore'`: Skip illegal substrings.
* <b>`replacement_char`</b>: The replacement codepoint to be used in place of invalid
  substrings in `input` when `errors='replace'`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `N+1` dimensional `int32` tensor with shape `[D1...DN, (num_chars)]`.
The returned tensor is a <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a> if `input` is a scalar, or a
<a href="../../tf/RaggedTensor.md"><code>tf.RaggedTensor</code></a> otherwise.


#### Example:

```
>>> input = [s.encode('utf8') for s in (u'G\xf6\xf6dnight', u'\U0001f60a')]
>>> tf.strings.unicode_split(input, 'UTF-8').to_list()
[[b'G', b'\xc3\xb6', b'\xc3\xb6', b'd', b'n', b'i', b'g', b'h', b't'],
 [b'\xf0\x9f\x98\x8a']]
```

## Compat aliases

* `tf.compat.v1.strings.unicode_split`
* `tf.compat.v2.strings.unicode_split`
