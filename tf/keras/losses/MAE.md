<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.losses.MAE" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.losses.MAE

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/losses.py">View source</a>



Computes the mean absolute error between labels and predictions.

**Aliases**: `tf.keras.losses.mae`, `tf.keras.losses.mean_absolute_error`, `tf.keras.metrics.MAE`, `tf.keras.metrics.mae`, `tf.keras.metrics.mean_absolute_error`, `tf.losses.MAE`, `tf.losses.mae`, `tf.losses.mean_absolute_error`, `tf.metrics.MAE`, `tf.metrics.mae`, `tf.metrics.mean_absolute_error`

``` python
tf.keras.losses.MAE(
    y_true,
    y_pred
)
```



<!-- Placeholder for "Used in" -->

`loss = abs(y_true - y_pred)`

#### Args:


* <b>`y_true`</b>: Ground truth values. shape = `[batch_size, d0, .. dN]`.
* <b>`y_pred`</b>: The predicted values. shape = `[batch_size, d0, .. dN]`.


#### Returns:

Mean absolute error values. shape = `[batch_size, d0, .. dN-1]`.


## Compat aliases

* `tf.compat.v1.keras.losses.MAE`
* `tf.compat.v1.keras.losses.mae`
* `tf.compat.v1.keras.losses.mean_absolute_error`
* `tf.compat.v1.keras.metrics.MAE`
* `tf.compat.v1.keras.metrics.mae`
* `tf.compat.v1.keras.metrics.mean_absolute_error`
* `tf.compat.v2.keras.losses.MAE`
* `tf.compat.v2.keras.losses.mae`
* `tf.compat.v2.keras.losses.mean_absolute_error`
* `tf.compat.v2.keras.metrics.MAE`
* `tf.compat.v2.keras.metrics.mae`
* `tf.compat.v2.keras.metrics.mean_absolute_error`
* `tf.compat.v2.losses.MAE`
* `tf.compat.v2.losses.mae`
* `tf.compat.v2.losses.mean_absolute_error`
* `tf.compat.v2.metrics.MAE`
* `tf.compat.v2.metrics.mae`
* `tf.compat.v2.metrics.mean_absolute_error`

