<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.erf" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.erf

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>



Computes the Gauss error function of `x` element-wise.

``` python
tf.math.erf(
    x,
    name=None
)
```



<!-- Placeholder for "Used in" -->


#### Args:


* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.

If `x` is a `SparseTensor`, returns
`SparseTensor(x.indices, tf.math.erf(x.values, ...), x.dense_shape)`


## Compat aliases

* `tf.compat.v1.erf`
* `tf.compat.v1.math.erf`
* `tf.compat.v2.math.erf`

