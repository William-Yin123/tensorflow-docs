<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.sqrt" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.sqrt

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/math_ops.py">View source</a>



Computes element-wise square root of the input tensor.

**Aliases**: `tf.sqrt`

``` python
tf.math.sqrt(
    x,
    name=None
)
```



<!-- Placeholder for "Used in" -->

Note: This operation does not support integer types.

```
>>> x = tf.constant([[4.0], [16.0]])
>>> tf.sqrt(x)
<tf.Tensor: shape=(2, 1), dtype=float32, numpy=
  array([[2.],
         [4.]], dtype=float32)>
>>> y = tf.constant([[-4.0], [16.0]])
>>> tf.sqrt(y)
<tf.Tensor: shape=(2, 1), dtype=float32, numpy=
  array([[nan],
         [ 4.]], dtype=float32)>
>>> z = tf.constant([[-1.0], [16.0]], dtype=tf.complex128)
>>> tf.sqrt(z)
<tf.Tensor: shape=(2, 1), dtype=complex128, numpy=
  array([[0.0+1.j],
         [4.0+0.j]])>
```

Note: In order to support complex complex, please provide an input tensor
of `complex64` or `complex128`.

#### Args:


* <b>`x`</b>: A <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a> of type `bfloat16`, `half`, `float32`, `float64`,
  `complex64`, `complex128`
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a> of same size, type and sparsity as `x`.

If `x` is a `SparseTensor`, returns
`SparseTensor(x.indices, tf.math.sqrt(x.values, ...), x.dense_shape)`


## Compat aliases

* `tf.compat.v1.math.sqrt`
* `tf.compat.v1.sqrt`
* `tf.compat.v2.math.sqrt`
* `tf.compat.v2.sqrt`

