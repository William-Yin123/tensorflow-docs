<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.nn.log_softmax" />
<meta itemprop="path" content="Stable" />
</div>

# tf.nn.log_softmax

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/nn_ops.py">View source</a>



Computes log softmax activations.

**Aliases**: `tf.math.log_softmax`

``` python
tf.nn.log_softmax(
    logits,
    axis=None,
    name=None
)
```



<!-- Placeholder for "Used in" -->

For each batch `i` and class `j` we have

    logsoftmax = logits - log(reduce_sum(exp(logits), axis))

#### Args:


* <b>`logits`</b>: A non-empty `Tensor`. Must be one of the following types: `half`,
  `float32`, `float64`.
* <b>`axis`</b>: The dimension softmax would be performed on. The default is -1 which
  indicates the last dimension.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `logits`. Same shape as `logits`.



#### Raises:


* <b>`InvalidArgumentError`</b>: if `logits` is empty or `axis` is beyond the last
  dimension of `logits`.

## Compat aliases

* `tf.compat.v2.math.log_softmax`
* `tf.compat.v2.nn.log_softmax`

