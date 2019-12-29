<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.strings.unicode_encode" />
<meta itemprop="path" content="Stable" />
</div>

# tf.strings.unicode_encode

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/ragged/ragged_string_ops.py">View source</a>



Encodes each sequence of Unicode code points in `input` into a string.

``` python
tf.strings.unicode_encode(
    input,
    output_encoding,
    errors='replace',
    replacement_char=65533,
    name=None
)
```



<!-- Placeholder for "Used in" -->

`result[i1...iN]` is the string formed by concatenating the Unicode
codepoints `input[1...iN, :]`, encoded using `output_encoding`.

#### Args:


* <b>`input`</b>: An `N+1` dimensional potentially ragged integer tensor with shape
  `[D1...DN, num_chars]`.
* <b>`output_encoding`</b>: Unicode encoding that should be used to encode each
  codepoint sequence.  Can be `"UTF-8"`, `"UTF-16-BE"`, or `"UTF-32-BE"`.
* <b>`errors`</b>: Specifies the response when an invalid codepoint is encountered
  (optional). One of:
        * `'replace'`: Replace invalid codepoint with the
          `replacement_char`. (default)
        * `'ignore'`: Skip invalid codepoints.
        * `'strict'`: Raise an exception for any invalid codepoint.
* <b>`replacement_char`</b>: The replacement character codepoint to be used in place of
  any invalid input when `errors='replace'`. Any valid unicode codepoint may
  be used. The default value is the default unicode replacement character
  which is 0xFFFD (U+65533).
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `N` dimensional `string` tensor with shape `[D1...DN]`.


#### Example:

```
>>> input = tf.ragged.constant(
...     [[71, 246, 246, 100, 110, 105, 103, 104, 116], [128522]])
>>> print(unicode_encode(input, 'UTF-8'))
tf.Tensor([b'G\xc3\xb6\xc3\xb6dnight' b'\xf0\x9f\x98\x8a'],
          shape=(2,), dtype=string)
```

## Compat aliases

* `tf.compat.v1.strings.unicode_encode`
* `tf.compat.v2.strings.unicode_encode`

