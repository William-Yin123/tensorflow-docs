<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.square" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.square

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>



Computes square of x element-wise.

**Aliases**: `tf.square`

``` python
tf.math.square(
    x,
    name=None
)
```



<!-- Placeholder for "Used in" -->

I.e., \\(y = x * x = x^2\\).

```
>>> tf.math.square([-2., 0., 3.])
<tf.Tensor: shape=(3,), dtype=float32, numpy=array([4., 0., 9.], dtype=float32)>
```

#### Args:


* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`, `int32`, `int64`, `complex64`, `complex128`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.

If `x` is a `SparseTensor`, returns
`SparseTensor(x.indices, tf.math.square(x.values, ...), x.dense_shape)`


## Compat aliases

* `tf.compat.v1.math.square`
* `tf.compat.v1.square`
* `tf.compat.v2.math.square`
* `tf.compat.v2.square`

