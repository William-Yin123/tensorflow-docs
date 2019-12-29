<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.math.softmax" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.math.softmax

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/nn_ops.py">View source</a>



Computes softmax activations. (deprecated arguments)

``` python
tf.compat.v1.math.softmax(
    logits,
    axis=None,
    name=None,
    dim=None
)
```



<!-- Placeholder for "Used in" -->

Warning: SOME ARGUMENTS ARE DEPRECATED: `(dim)`. They will be removed in a future version.
Instructions for updating:
dim is deprecated, use axis instead

This function performs the equivalent of

    softmax = tf.exp(logits) / tf.reduce_sum(tf.exp(logits), axis)

See: https://en.wikipedia.org/wiki/Softmax_function

#### Example usage:


>>> tf.nn.softmax([-1, 0., 1.])
<tf.Tensor: shape=(3,), dtype=float32,
numpy=array([0.09003057, 0.24472848, 0.66524094], dtype=float32)>

#### Args:


* <b>`logits`</b>: A non-empty `Tensor`, or an object whose type has a registered
  `Tensor` conversion function. Must be one of the following types:
  `half`,`float32`, `float64`. See also `convert_to_tensor`
* <b>`axis`</b>: The dimension softmax would be performed on. The default is -1 which
  indicates the last dimension.
* <b>`name`</b>: A name for the operation (optional).
* <b>`dim`</b>: Deprecated alias for `axis`.


#### Returns:

A `Tensor`. Has the same type and shape as `logits`.



#### Raises:


* <b>`InvalidArgumentError`</b>: if `logits` is empty or `axis` is beyond the last
  dimension of `logits`.
* <b>`TypeError`</b>: If no conversion function is registered for `logits` to
  Tensor.
* <b>`RuntimeError`</b>: If a registered conversion function returns an invalid
  value.

## Compat aliases

* `tf.compat.v1.nn.softmax`

