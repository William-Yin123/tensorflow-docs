<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.losses.LogCosh" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="from_config"/>
<meta itemprop="property" content="get_config"/>
</div>

# tf.keras.losses.LogCosh

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/losses.py">View source</a>



## Class `LogCosh`

Computes the logarithm of the hyperbolic cosine of the prediction error.



**Aliases**: `tf.losses.LogCosh`

<!-- Placeholder for "Used in" -->

`logcosh = log((exp(x) + exp(-x))/2)`,
where x is the error `y_pred - y_true`.

#### Usage:



```
>>> l = tf.keras.losses.LogCosh()
>>> loss = l([[0., 1.], [0., 0.]], [[1., 1.], [0., 0.]])
>>> loss.numpy()
0.10844523
```

```
>>> loss = l([[0., 1.], [0., 0.]], [[1., 1.], [0., 0.]],
...          sample_weight=[1., 0.])
>>> loss.numpy()
0.10844523
```

Usage with the `compile` API:

```python
model = tf.keras.Model(inputs, outputs)
model.compile('sgd', loss=tf.keras.losses.LogCosh())
```

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/losses.py">View source</a>

``` python
__init__(
    reduction=losses_utils.ReductionV2.AUTO,
    name='logcosh'
)
```

Initialize self.  See help(type(self)) for accurate signature.




## Methods

<h3 id="__call__"><code>__call__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/losses.py">View source</a>

``` python
__call__(
    y_true,
    y_pred,
    sample_weight=None
)
```

Invokes the `Loss` instance.


#### Args:


* <b>`y_true`</b>: Ground truth values. shape = `[batch_size, d0, .. dN]`
* <b>`y_pred`</b>: The predicted values. shape = `[batch_size, d0, .. dN]`
* <b>`sample_weight`</b>: Optional `sample_weight` acts as a
  coefficient for the loss. If a scalar is provided, then the loss is
  simply scaled by the given value. If `sample_weight` is a tensor of size
  `[batch_size]`, then the total loss for each sample of the batch is
  rescaled by the corresponding element in the `sample_weight` vector. If
  the shape of `sample_weight` is `[batch_size, d0, .. dN-1]` (or can be
  broadcasted to this shape), then each loss element of `y_pred` is scaled
  by the corresponding value of `sample_weight`. (Note on`dN-1`: all loss
  functions reduce by 1 dimension, usually axis=-1.)


#### Returns:

Weighted loss float `Tensor`. If `reduction` is `NONE`, this has
  shape `[batch_size, d0, .. dN-1]`; otherwise, it is scalar. (Note `dN-1`
  because all loss functions reduce by 1 dimension, usually axis=-1.)



#### Raises:


* <b>`ValueError`</b>: If the shape of `sample_weight` is invalid.

<h3 id="from_config"><code>from_config</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/losses.py">View source</a>

``` python
from_config(
    cls,
    config
)
```

Instantiates a `Loss` from its config (output of `get_config()`).


#### Args:


* <b>`config`</b>: Output of `get_config()`.


#### Returns:

A `Loss` instance.


<h3 id="get_config"><code>get_config</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/losses.py">View source</a>

``` python
get_config()
```








## Compat aliases

* `tf.compat.v1.keras.losses.LogCosh`
* `tf.compat.v2.keras.losses.LogCosh`
* `tf.compat.v2.losses.LogCosh`

