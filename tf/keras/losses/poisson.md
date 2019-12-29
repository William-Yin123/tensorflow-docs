<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.losses.poisson" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.losses.poisson

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/losses.py">View source</a>



Computes the Poisson loss between y_true and y_pred.

**Aliases**: `tf.keras.metrics.poisson`, `tf.losses.poisson`, `tf.metrics.poisson`

``` python
tf.keras.losses.poisson(
    y_true,
    y_pred
)
```



<!-- Placeholder for "Used in" -->

The Poisson loss is the mean of the elements of the `Tensor`
`y_pred - y_true * log(y_pred)`.

#### Args:


* <b>`y_true`</b>: Ground truth values. shape = `[batch_size, d0, .. dN]`.
* <b>`y_pred`</b>: The predicted values. shape = `[batch_size, d0, .. dN]`.


#### Returns:

Poisson loss value. shape = `[batch_size, d0, .. dN-1]`.



#### Raises:


* <b>`InvalidArgumentError`</b>: If `y_true` and `y_pred` have incompatible shapes.

## Compat aliases

* `tf.compat.v1.keras.losses.poisson`
* `tf.compat.v1.keras.metrics.poisson`
* `tf.compat.v2.keras.losses.poisson`
* `tf.compat.v2.keras.metrics.poisson`
* `tf.compat.v2.losses.poisson`
* `tf.compat.v2.metrics.poisson`

