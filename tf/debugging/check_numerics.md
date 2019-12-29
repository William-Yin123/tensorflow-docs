<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.debugging.check_numerics" />
<meta itemprop="path" content="Stable" />
</div>

# tf.debugging.check_numerics

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>



Checks a tensor for NaN and Inf values.

``` python
tf.debugging.check_numerics(
    tensor,
    message,
    name=None
)
```



<!-- Placeholder for "Used in" -->

When run, reports an `InvalidArgument` error if `tensor` has any values
that are not a number (NaN) or infinity (Inf). Otherwise, passes `tensor` as-is.

#### Args:


* <b>`tensor`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`.
* <b>`message`</b>: A `string`. Prefix of the error message.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `tensor`.


## Compat aliases

* `tf.compat.v1.check_numerics`
* `tf.compat.v1.debugging.check_numerics`
* `tf.compat.v2.debugging.check_numerics`

