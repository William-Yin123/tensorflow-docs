<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.nn.l2_loss" />
<meta itemprop="path" content="Stable" />
</div>

# tf.nn.l2_loss

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>



L2 Loss.

``` python
tf.nn.l2_loss(
    t,
    name=None
)
```



<!-- Placeholder for "Used in" -->

Computes half the L2 norm of a tensor without the `sqrt`:

    output = sum(t ** 2) / 2

#### Args:


* <b>`t`</b>: A `Tensor`. Must be one of the following types: `half`, `bfloat16`, `float32`, `float64`.
  Typically 2-D, but may have any dimensions.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `t`.


## Compat aliases

* `tf.compat.v1.nn.l2_loss`
* `tf.compat.v2.nn.l2_loss`

