<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.losses.MSE" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.losses.MSE

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/losses.py">View source</a>



Computes the mean squared error between labels and predictions.

**Aliases**: `tf.keras.losses.mean_squared_error`, `tf.keras.losses.mse`, `tf.keras.metrics.MSE`, `tf.keras.metrics.mean_squared_error`, `tf.keras.metrics.mse`, `tf.losses.MSE`, `tf.losses.mean_squared_error`, `tf.losses.mse`, `tf.metrics.MSE`, `tf.metrics.mean_squared_error`, `tf.metrics.mse`

``` python
tf.keras.losses.MSE(
    y_true,
    y_pred
)
```



<!-- Placeholder for "Used in" -->

`loss = square(y_true - y_pred)`

#### Args:


* <b>`y_true`</b>: Ground truth values. shape = `[batch_size, d0, .. dN]`.
* <b>`y_pred`</b>: The predicted values. shape = `[batch_size, d0, .. dN]`.


#### Returns:

Mean squared error values. shape = `[batch_size, d0, .. dN-1]`.


## Compat aliases

* `tf.compat.v1.keras.losses.MSE`
* `tf.compat.v1.keras.losses.mean_squared_error`
* `tf.compat.v1.keras.losses.mse`
* `tf.compat.v1.keras.metrics.MSE`
* `tf.compat.v1.keras.metrics.mean_squared_error`
* `tf.compat.v1.keras.metrics.mse`
* `tf.compat.v2.keras.losses.MSE`
* `tf.compat.v2.keras.losses.mean_squared_error`
* `tf.compat.v2.keras.losses.mse`
* `tf.compat.v2.keras.metrics.MSE`
* `tf.compat.v2.keras.metrics.mean_squared_error`
* `tf.compat.v2.keras.metrics.mse`
* `tf.compat.v2.losses.MSE`
* `tf.compat.v2.losses.mean_squared_error`
* `tf.compat.v2.losses.mse`
* `tf.compat.v2.metrics.MSE`
* `tf.compat.v2.metrics.mean_squared_error`
* `tf.compat.v2.metrics.mse`

