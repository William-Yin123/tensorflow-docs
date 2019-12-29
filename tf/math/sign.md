<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.sign" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.sign

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>



Returns an element-wise indication of the sign of a number.

**Aliases**: `tf.sign`

``` python
tf.math.sign(
    x,
    name=None
)
```



<!-- Placeholder for "Used in" -->

`y = sign(x) = -1` if `x < 0`; 0 if `x == 0`; 1 if `x > 0`.

For complex numbers, `y = sign(x) = x / |x|` if `x != 0`, otherwise `y = 0`.

#### Example usage:


>>> tf.math.sign([0., 2., -3.])
<tf.Tensor: shape=(3,), dtype=float32, numpy=array([ 0.,  1., -1.], dtype=float32)>

#### Args:


* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`, `int32`, `int64`, `complex64`, `complex128`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.

If `x` is a `SparseTensor`, returns
`SparseTensor(x.indices, tf.math.sign(x.values, ...), x.dense_shape)`


## Compat aliases

* `tf.compat.v1.math.sign`
* `tf.compat.v1.sign`
* `tf.compat.v2.math.sign`
* `tf.compat.v2.sign`

