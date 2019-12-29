<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.losses.sparse_categorical_crossentropy" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.losses.sparse_categorical_crossentropy

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/losses.py">View source</a>



Computes the sparse categorical crossentropy loss.

**Aliases**: `tf.keras.metrics.sparse_categorical_crossentropy`, `tf.losses.sparse_categorical_crossentropy`, `tf.metrics.sparse_categorical_crossentropy`

``` python
tf.keras.losses.sparse_categorical_crossentropy(
    y_true,
    y_pred,
    from_logits=False,
    axis=-1
)
```



<!-- Placeholder for "Used in" -->


#### Args:


* <b>`y_true`</b>: Ground truth values.
* <b>`y_pred`</b>: The predicted values.
* <b>`from_logits`</b>: Whether `y_pred` is expected to be a logits tensor. By default,
  we assume that `y_pred` encodes a probability distribution.
* <b>`axis`</b>: (Optional) Defaults to -1. The dimension along which the entropy is
  computed.


#### Returns:

Sparse categorical crossentropy loss value.


## Compat aliases

* `tf.compat.v1.keras.losses.sparse_categorical_crossentropy`
* `tf.compat.v1.keras.metrics.sparse_categorical_crossentropy`
* `tf.compat.v2.keras.losses.sparse_categorical_crossentropy`
* `tf.compat.v2.keras.metrics.sparse_categorical_crossentropy`
* `tf.compat.v2.losses.sparse_categorical_crossentropy`
* `tf.compat.v2.metrics.sparse_categorical_crossentropy`

