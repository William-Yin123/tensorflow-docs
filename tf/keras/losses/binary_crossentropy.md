<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.losses.binary_crossentropy" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.losses.binary_crossentropy

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/losses.py">View source</a>



Computes the binary crossentropy loss.

**Aliases**: `tf.keras.metrics.binary_crossentropy`, `tf.losses.binary_crossentropy`, `tf.metrics.binary_crossentropy`

``` python
tf.keras.losses.binary_crossentropy(
    y_true,
    y_pred,
    from_logits=False,
    label_smoothing=0
)
```



<!-- Placeholder for "Used in" -->


#### Args:


* <b>`y_true`</b>: Ground truth values. shape = `[batch_size, d0, .. dN]`.
* <b>`y_pred`</b>: The predicted values. shape = `[batch_size, d0, .. dN]`.
* <b>`from_logits`</b>: Whether `y_pred` is expected to be a logits tensor. By default,
  we assume that `y_pred` encodes a probability distribution.
* <b>`label_smoothing`</b>: Float in [0, 1]. If > `0` then smooth the labels.


#### Returns:

Binary crossentropy loss value. shape = `[batch_size, d0, .. dN-1]`.


## Compat aliases

* `tf.compat.v1.keras.losses.binary_crossentropy`
* `tf.compat.v1.keras.metrics.binary_crossentropy`
* `tf.compat.v2.keras.losses.binary_crossentropy`
* `tf.compat.v2.keras.metrics.binary_crossentropy`
* `tf.compat.v2.losses.binary_crossentropy`
* `tf.compat.v2.metrics.binary_crossentropy`

