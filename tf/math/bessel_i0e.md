<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.bessel_i0e" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.bessel_i0e

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>



Computes the Bessel i0e function of `x` element-wise.

``` python
tf.math.bessel_i0e(
    x,
    name=None
)
```



<!-- Placeholder for "Used in" -->

Exponentially scaled modified Bessel function of order 0 defined as
`bessel_i0e(x) = exp(-abs(x)) bessel_i0(x)`.

This function is faster and numerically stabler than `bessel_i0(x)`.

#### Args:


* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.

If `x` is a `SparseTensor`, returns
`SparseTensor(x.indices, tf.math.bessel_i0e(x.values, ...), x.dense_shape)`


## Compat aliases

* `tf.compat.v1.math.bessel_i0e`
* `tf.compat.v2.math.bessel_i0e`

