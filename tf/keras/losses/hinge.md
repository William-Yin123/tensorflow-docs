<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.losses.hinge" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.losses.hinge

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/losses.py">View source</a>



Computes the hinge loss between `y_true` and `y_pred`.

**Aliases**: `tf.keras.metrics.hinge`, `tf.losses.hinge`, `tf.metrics.hinge`

``` python
tf.keras.losses.hinge(
    y_true,
    y_pred
)
```



<!-- Placeholder for "Used in" -->

`loss = maximum(1 - y_true * y_pred, 0)`

#### Args:


* <b>`y_true`</b>: The ground truth values. `y_true` values are expected to be -1 or 1.
  If binary (0 or 1) labels are provided they will be converted to -1 or 1.
  shape = `[batch_size, d0, .. dN]`.
* <b>`y_pred`</b>: The predicted values. shape = `[batch_size, d0, .. dN]`.


#### Returns:

Hinge loss values. shape = `[batch_size, d0, .. dN-1]`.


## Compat aliases

* `tf.compat.v1.keras.losses.hinge`
* `tf.compat.v1.keras.metrics.hinge`
* `tf.compat.v2.keras.losses.hinge`
* `tf.compat.v2.keras.metrics.hinge`
* `tf.compat.v2.losses.hinge`
* `tf.compat.v2.metrics.hinge`

