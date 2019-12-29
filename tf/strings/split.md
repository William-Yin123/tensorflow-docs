<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.strings.split" />
<meta itemprop="path" content="Stable" />
</div>

# tf.strings.split

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/ragged/ragged_string_ops.py">View source</a>



Split elements of `input` based on `sep` into a `RaggedTensor`.

``` python
tf.strings.split(
    input,
    sep=None,
    maxsplit=-1,
    name=None
)
```



<!-- Placeholder for "Used in" -->

Let N be the size of `input` (typically N will be the batch size). Split each
element of `input` based on `sep` and return a `SparseTensor` or
`RaggedTensor` containing the split tokens. Empty tokens are ignored.

#### Example:



```
>>> tf.strings.split('hello world').numpy()
 array([b'hello', b'world'], dtype=object)
>>> tf.strings.split(['hello world', 'a b c'])
<tf.RaggedTensor [[b'hello', b'world'], [b'a', b'b', b'c']]>
```

If `sep` is given, consecutive delimiters are not grouped together and are
deemed to delimit empty strings. For example, `input` of `"1<>2<><>3"` and
`sep` of `"<>"` returns `["1", "2", "", "3"]`. If `sep` is None or an empty
string, consecutive whitespace are regarded as a single separator, and the
result will contain no empty strings at the start or end if the string has
leading or trailing whitespace.

Note that the above mentioned behavior matches python's str.split.

#### Args:


* <b>`input`</b>: A string `Tensor` of rank `N`, the strings to split.  If
  `rank(input)` is not known statically, then it is assumed to be `1`.
* <b>`sep`</b>: `0-D` string `Tensor`, the delimiter string.
* <b>`maxsplit`</b>: An `int`. If `maxsplit > 0`, limit of the split of the result.
* <b>`name`</b>: A name for the operation (optional).


#### Raises:


* <b>`ValueError`</b>: If sep is not a string.


#### Returns:

A `RaggedTensor` of rank `N+1`, the strings split according to the
delimiter.


## Compat aliases

* `tf.compat.v2.strings.split`

