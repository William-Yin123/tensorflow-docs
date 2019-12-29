<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.losses.KLD" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.losses.KLD

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/losses.py">View source</a>



Computes Kullback-Leibler divergence loss between `y_true` and `y_pred`.

**Aliases**: `tf.keras.losses.kld`, `tf.keras.losses.kullback_leibler_divergence`, `tf.keras.metrics.KLD`, `tf.keras.metrics.kld`, `tf.keras.metrics.kullback_leibler_divergence`, `tf.losses.KLD`, `tf.losses.kld`, `tf.losses.kullback_leibler_divergence`, `tf.metrics.KLD`, `tf.metrics.kld`, `tf.metrics.kullback_leibler_divergence`

``` python
tf.keras.losses.KLD(
    y_true,
    y_pred
)
```



<!-- Placeholder for "Used in" -->

`loss = y_true * log(y_true / y_pred)`

See: https://en.wikipedia.org/wiki/Kullback%E2%80%93Leibler_divergence

#### Usage:



```python
loss = tf.keras.losses.KLD([.4, .9, .2], [.5, .8, .12])
print('Loss: ', loss.numpy())  # Loss: 0.11891246
```

#### Args:


* <b>`y_true`</b>: Tensor of true targets.
* <b>`y_pred`</b>: Tensor of predicted targets.


#### Returns:

A `Tensor` with loss.



#### Raises:


* <b>`TypeError`</b>: If `y_true` cannot be cast to the `y_pred.dtype`.

## Compat aliases

* `tf.compat.v1.keras.losses.KLD`
* `tf.compat.v1.keras.losses.kld`
* `tf.compat.v1.keras.losses.kullback_leibler_divergence`
* `tf.compat.v1.keras.metrics.KLD`
* `tf.compat.v1.keras.metrics.kld`
* `tf.compat.v1.keras.metrics.kullback_leibler_divergence`
* `tf.compat.v2.keras.losses.KLD`
* `tf.compat.v2.keras.losses.kld`
* `tf.compat.v2.keras.losses.kullback_leibler_divergence`
* `tf.compat.v2.keras.metrics.KLD`
* `tf.compat.v2.keras.metrics.kld`
* `tf.compat.v2.keras.metrics.kullback_leibler_divergence`
* `tf.compat.v2.losses.KLD`
* `tf.compat.v2.losses.kld`
* `tf.compat.v2.losses.kullback_leibler_divergence`
* `tf.compat.v2.metrics.KLD`
* `tf.compat.v2.metrics.kld`
* `tf.compat.v2.metrics.kullback_leibler_divergence`

