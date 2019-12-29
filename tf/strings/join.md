<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.strings.join" />
<meta itemprop="path" content="Stable" />
</div>

# tf.strings.join

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>



Joins the strings in the given list of string tensors into one tensor;

``` python
tf.strings.join(
    inputs,
    separator='',
    name=None
)
```



<!-- Placeholder for "Used in" -->

with the given separator (default is an empty separator).

#### Examples:


>>> s = ["hello", "world", "tensorflow"]
>>> tf.strings.join(s, " ")
<tf.Tensor: id=11, shape=(), dtype=string, numpy=b'hello world tensorflow'>

#### Args:


* <b>`inputs`</b>: A list of at least 1 `Tensor` objects with type `string`.
  A list of string tensors.  The tensors must all have the same shape,
  or be scalars.  Scalars may be mixed in; these will be broadcast to the shape
  of non-scalar inputs.
* <b>`separator`</b>: An optional `string`. Defaults to `""`.
  string, an optional join separator.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `string`.


## Compat aliases

* `tf.compat.v1.string_join`
* `tf.compat.v1.strings.join`
* `tf.compat.v2.strings.join`

