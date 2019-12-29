<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.nn.softsign" />
<meta itemprop="path" content="Stable" />
</div>

# tf.nn.softsign

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>



Computes softsign: `features / (abs(features) + 1)`.

**Aliases**: `tf.math.softsign`

``` python
tf.nn.softsign(
    features,
    name=None
)
```



<!-- Placeholder for "Used in" -->


#### Args:


* <b>`features`</b>: A `Tensor`. Must be one of the following types: `half`, `bfloat16`, `float32`, `float64`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `features`.


## Compat aliases

* `tf.compat.v1.math.softsign`
* `tf.compat.v1.nn.softsign`
* `tf.compat.v2.math.softsign`
* `tf.compat.v2.nn.softsign`

