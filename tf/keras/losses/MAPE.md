<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.losses.MAPE" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.losses.MAPE

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/losses.py">View source</a>



Computes the mean absolute percentage error between `y_true` and `y_pred`.

**Aliases**: `tf.keras.losses.mape`, `tf.keras.losses.mean_absolute_percentage_error`, `tf.keras.metrics.MAPE`, `tf.keras.metrics.mape`, `tf.keras.metrics.mean_absolute_percentage_error`, `tf.losses.MAPE`, `tf.losses.mape`, `tf.losses.mean_absolute_percentage_error`, `tf.metrics.MAPE`, `tf.metrics.mape`, `tf.metrics.mean_absolute_percentage_error`

``` python
tf.keras.losses.MAPE(
    y_true,
    y_pred
)
```



<!-- Placeholder for "Used in" -->

`loss = 100 * abs(y_true - y_pred) / y_true`

#### Args:


* <b>`y_true`</b>: Ground truth values. shape = `[batch_size, d0, .. dN]`.
* <b>`y_pred`</b>: The predicted values. shape = `[batch_size, d0, .. dN]`.


#### Returns:

Mean absolute percentage error values. shape = `[batch_size, d0, .. dN-1]`.


## Compat aliases

* `tf.compat.v1.keras.losses.MAPE`
* `tf.compat.v1.keras.losses.mape`
* `tf.compat.v1.keras.losses.mean_absolute_percentage_error`
* `tf.compat.v1.keras.metrics.MAPE`
* `tf.compat.v1.keras.metrics.mape`
* `tf.compat.v1.keras.metrics.mean_absolute_percentage_error`
* `tf.compat.v2.keras.losses.MAPE`
* `tf.compat.v2.keras.losses.mape`
* `tf.compat.v2.keras.losses.mean_absolute_percentage_error`
* `tf.compat.v2.keras.metrics.MAPE`
* `tf.compat.v2.keras.metrics.mape`
* `tf.compat.v2.keras.metrics.mean_absolute_percentage_error`
* `tf.compat.v2.losses.MAPE`
* `tf.compat.v2.losses.mape`
* `tf.compat.v2.losses.mean_absolute_percentage_error`
* `tf.compat.v2.metrics.MAPE`
* `tf.compat.v2.metrics.mape`
* `tf.compat.v2.metrics.mean_absolute_percentage_error`

