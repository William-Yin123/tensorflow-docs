<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.losses.logcosh" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.losses.logcosh

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/losses.py">View source</a>



Logarithm of the hyperbolic cosine of the prediction error.

**Aliases**: `tf.losses.logcosh`

``` python
tf.keras.losses.logcosh(
    y_true,
    y_pred
)
```



<!-- Placeholder for "Used in" -->

`log(cosh(x))` is approximately equal to `(x ** 2) / 2` for small `x` and
to `abs(x) - log(2)` for large `x`. This means that 'logcosh' works mostly
like the mean squared error, but will not be so strongly affected by the
occasional wildly incorrect prediction.

#### Args:


* <b>`y_true`</b>: Ground truth values. shape = `[batch_size, d0, .. dN]`.
* <b>`y_pred`</b>: The predicted values. shape = `[batch_size, d0, .. dN]`.


#### Returns:

Logcosh error values. shape = `[batch_size, d0, .. dN-1]`.


## Compat aliases

* `tf.compat.v1.keras.losses.logcosh`
* `tf.compat.v2.keras.losses.logcosh`
* `tf.compat.v2.losses.logcosh`

