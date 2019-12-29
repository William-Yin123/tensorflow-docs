<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.zeta" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.zeta

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>



Compute the Hurwitz zeta function \\(\zeta(x, q)\\).

``` python
tf.math.zeta(
    x,
    q,
    name=None
)
```



<!-- Placeholder for "Used in" -->

The Hurwitz zeta function is defined as:


\\(\zeta(x, q) = \sum_{n=0}^{\infty} (q + n)^{-x}\\)

#### Args:


* <b>`x`</b>: A `Tensor`. Must be one of the following types: `float32`, `float64`.
* <b>`q`</b>: A `Tensor`. Must have the same type as `x`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.


## Compat aliases

* `tf.compat.v1.math.zeta`
* `tf.compat.v1.zeta`
* `tf.compat.v2.math.zeta`

