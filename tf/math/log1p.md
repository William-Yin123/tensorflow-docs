<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.log1p" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.log1p

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>



Computes natural logarithm of (1 + x) element-wise.

``` python
tf.math.log1p(
    x,
    name=None
)
```



<!-- Placeholder for "Used in" -->

I.e., \\(y = \log_e (1 + x)\\).

#### Example:


>>> x = tf.constant([0, 0.5, 1, 5])
>>> tf.math.log1p(x)
<tf.Tensor: shape=(4,), dtype=float32, numpy=array([0.       , 0.4054651, 0.6931472, 1.7917595], dtype=float32)>

#### Args:


* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`, `complex64`, `complex128`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.


## Compat aliases

* `tf.compat.v1.log1p`
* `tf.compat.v1.math.log1p`
* `tf.compat.v2.math.log1p`

