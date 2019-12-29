<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.reciprocal" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.reciprocal

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>



Computes the reciprocal of x element-wise.

``` python
tf.math.reciprocal(
    x,
    name=None
)
```



<!-- Placeholder for "Used in" -->

I.e., \\(y = 1 / x\\).

#### Args:


* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`, `int32`, `int64`, `complex64`, `complex128`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.


## Compat aliases

* `tf.compat.v1.math.reciprocal`
* `tf.compat.v1.reciprocal`
* `tf.compat.v2.math.reciprocal`

