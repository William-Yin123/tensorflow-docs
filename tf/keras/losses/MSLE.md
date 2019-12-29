<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.losses.MSLE" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.losses.MSLE

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/losses.py">View source</a>



Computes the mean squared logarithmic error between `y_true` and `y_pred`.

**Aliases**: `tf.keras.losses.mean_squared_logarithmic_error`, `tf.keras.losses.msle`, `tf.keras.metrics.MSLE`, `tf.keras.metrics.mean_squared_logarithmic_error`, `tf.keras.metrics.msle`, `tf.losses.MSLE`, `tf.losses.mean_squared_logarithmic_error`, `tf.losses.msle`, `tf.metrics.MSLE`, `tf.metrics.mean_squared_logarithmic_error`, `tf.metrics.msle`

``` python
tf.keras.losses.MSLE(
    y_true,
    y_pred
)
```



<!-- Placeholder for "Used in" -->

`loss = square(log(y_true) - log(y_pred))`

#### Args:


* <b>`y_true`</b>: Ground truth values. shape = `[batch_size, d0, .. dN]`.
* <b>`y_pred`</b>: The predicted values. shape = `[batch_size, d0, .. dN]`.


#### Returns:

Mean squared logarithmic error values. shape = `[batch_size, d0, .. dN-1]`.


## Compat aliases

* `tf.compat.v1.keras.losses.MSLE`
* `tf.compat.v1.keras.losses.mean_squared_logarithmic_error`
* `tf.compat.v1.keras.losses.msle`
* `tf.compat.v1.keras.metrics.MSLE`
* `tf.compat.v1.keras.metrics.mean_squared_logarithmic_error`
* `tf.compat.v1.keras.metrics.msle`
* `tf.compat.v2.keras.losses.MSLE`
* `tf.compat.v2.keras.losses.mean_squared_logarithmic_error`
* `tf.compat.v2.keras.losses.msle`
* `tf.compat.v2.keras.metrics.MSLE`
* `tf.compat.v2.keras.metrics.mean_squared_logarithmic_error`
* `tf.compat.v2.keras.metrics.msle`
* `tf.compat.v2.losses.MSLE`
* `tf.compat.v2.losses.mean_squared_logarithmic_error`
* `tf.compat.v2.losses.msle`
* `tf.compat.v2.metrics.MSLE`
* `tf.compat.v2.metrics.mean_squared_logarithmic_error`
* `tf.compat.v2.metrics.msle`

