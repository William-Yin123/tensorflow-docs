<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.digamma" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.digamma

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>



Computes Psi, the derivative of Lgamma (the log of the absolute value of

``` python
tf.math.digamma(
    x,
    name=None
)
```



<!-- Placeholder for "Used in" -->

`Gamma(x)`), element-wise.

#### Args:


* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.


## Compat aliases

* `tf.compat.v1.digamma`
* `tf.compat.v1.math.digamma`
* `tf.compat.v2.math.digamma`

