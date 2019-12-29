<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.ones_like" />
<meta itemprop="path" content="Stable" />
</div>

# tf.ones_like

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/array_ops.py">View source</a>



Creates a tensor of all ones that has the same shape as the input.

``` python
tf.ones_like(
    input,
    dtype=None,
    name=None
)
```



<!-- Placeholder for "Used in" -->

Given a single tensor (`tensor`), this operation returns a tensor of the
same type and shape as `tensor` with all elements set to 1. Optionally,
you can use `dtype` to specify a new type for the returned tensor.

#### For example:



```
>>> tensor = tf.constant([[1, 2, 3], [4, 5, 6]])
>>> tf.ones_like(tensor)
<tf.Tensor: shape=(2, 3), dtype=int32, numpy=
  array([[1, 1, 1],
         [1, 1, 1]], dtype=int32)>
```

#### Args:


* <b>`input`</b>: A `Tensor`.
* <b>`dtype`</b>: A type for the returned `Tensor`. Must be `float16`, `float32`,
  `float64`, `int8`, `uint8`, `int16`, `uint16`, `int32`, `int64`,
  `complex64`, `complex128`, `bool` or `string`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` with all elements set to one.


## Compat aliases

* `tf.compat.v2.ones_like`

