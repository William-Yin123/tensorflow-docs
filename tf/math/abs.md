<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.abs" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.abs

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/math_ops.py">View source</a>



Computes the absolute value of a tensor.

**Aliases**: `tf.abs`

``` python
tf.math.abs(
    x,
    name=None
)
```



<!-- Placeholder for "Used in" -->

Given a tensor of integer or floating-point values, this operation returns a
tensor of the same type, where each element contains the absolute value of the
corresponding element in the input.

Given a tensor `x` of complex numbers, this operation returns a tensor of type
`float32` or `float64` that is the absolute value of each element in `x`. For
a complex number \\(a + bj\\), its absolute value is computed as \\(\sqrt{a^2
+ b^2}\\).  For example:

```
>>> x = tf.constant([[-2.25 + 4.75j], [-3.25 + 5.75j]])
>>> tf.abs(x)
<tf.Tensor: shape=(2, 1), dtype=float64, numpy=
array([[5.25594901],
       [6.60492241]])>
```

#### Args:


* <b>`x`</b>: A `Tensor` or `SparseTensor` of type `float16`, `float32`, `float64`,
  `int32`, `int64`, `complex64` or `complex128`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` or `SparseTensor` of the same size, type and sparsity as `x`,
  with absolute values. Note, for `complex64` or `complex128` input, the
  returned `Tensor` will be of type `float32` or `float64`, respectively.

If `x` is a `SparseTensor`, returns
`SparseTensor(x.indices, tf.math.abs(x.values, ...), x.dense_shape)`


## Compat aliases

* `tf.compat.v1.abs`
* `tf.compat.v1.math.abs`
* `tf.compat.v2.abs`
* `tf.compat.v2.math.abs`

