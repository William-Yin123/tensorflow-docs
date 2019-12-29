<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.tile" />
<meta itemprop="path" content="Stable" />
</div>

# tf.tile

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>



Constructs a tensor by tiling a given tensor.

``` python
tf.tile(
    input,
    multiples,
    name=None
)
```



<!-- Placeholder for "Used in" -->

This operation creates a new tensor by replicating `input` `multiples` times.
The output tensor's i'th dimension has `input.dims(i) * multiples[i]` elements,
and the values of `input` are replicated `multiples[i]` times along the 'i'th
dimension. For example, tiling `[a b c d]` by `[2]` produces
`[a b c d a b c d]`.

```
>>> a = tf.constant([[1,2,3],[4,5,6]], tf.int32)
>>> b = tf.constant([1,2], tf.int32)
>>> tf.tile(a, b)
<tf.Tensor: shape=(2, 6), dtype=int32, numpy=
array([[1, 2, 3, 1, 2, 3],
       [4, 5, 6, 4, 5, 6]], dtype=int32)>
>>> c = tf.constant([2,1], tf.int32)
>>> tf.tile(a, c)
<tf.Tensor: shape=(4, 3), dtype=int32, numpy=
array([[1, 2, 3],
       [4, 5, 6],
       [1, 2, 3],
       [4, 5, 6]], dtype=int32)>
>>> d = tf.constant([2,2], tf.int32)
>>> tf.tile(a, d)
<tf.Tensor: shape=(4, 6), dtype=int32, numpy=
array([[1, 2, 3, 1, 2, 3],
       [4, 5, 6, 4, 5, 6],
       [1, 2, 3, 1, 2, 3],
       [4, 5, 6, 4, 5, 6]], dtype=int32)>
```

#### Args:


* <b>`input`</b>: A `Tensor`. 1-D or higher.
* <b>`multiples`</b>: A `Tensor`. Must be one of the following types: `int32`, `int64`.
  1-D. Length must be the same as the number of dimensions in `input`
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `input`.


## Compat aliases

* `tf.compat.v1.manip.tile`
* `tf.compat.v1.tile`
* `tf.compat.v2.tile`

