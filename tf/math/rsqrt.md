<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.rsqrt" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.rsqrt

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>



Computes reciprocal of square root of x element-wise.

``` python
tf.math.rsqrt(
    x,
    name=None
)
```



<!-- Placeholder for "Used in" -->

I.e., \\(y = 1 / \sqrt{x}\\).

#### Example:


>>> x = tf.constant([2., 0., -2.])
>>> tf.math.rsqrt(x)
<tf.Tensor: shape=(3,), dtype=float32, numpy=array([0.70710677,        inf,        nan], dtype=float32)>

#### Args:


* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`, `complex64`, `complex128`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.


## Compat aliases

* `tf.compat.v1.math.rsqrt`
* `tf.compat.v1.rsqrt`
* `tf.compat.v2.math.rsqrt`

