<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.metrics.RootMeanSquaredError" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="__new__"/>
<meta itemprop="property" content="reset_states"/>
<meta itemprop="property" content="result"/>
<meta itemprop="property" content="update_state"/>
</div>

# tf.keras.metrics.RootMeanSquaredError

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/metrics.py">View source</a>



## Class `RootMeanSquaredError`

Computes root mean squared error metric between `y_true` and `y_pred`.

Inherits From: [`Mean`](../../../tf/keras/metrics/Mean.md)

**Aliases**: `tf.metrics.RootMeanSquaredError`

<!-- Placeholder for "Used in" -->


#### Usage:



```
>>> m = tf.keras.metrics.RootMeanSquaredError()
>>> _ = m.update_state([[0, 1], [0, 0]], [[1, 1], [0, 0]])
>>> m.result().numpy()
0.5
```

```
>>> m.reset_states()
>>> _ = m.update_state([[0, 1], [0, 0]], [[1, 1], [0, 0]],
...                    sample_weight=[1, 0])
>>> m.result().numpy()
0.70710677
```

Usage with tf.keras API:

```python
model = tf.keras.Model(inputs, outputs)
model.compile(
    'sgd',
    loss='mse',
    metrics=[tf.keras.metrics.RootMeanSquaredError()])
```

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/metrics.py">View source</a>

``` python
__init__(
    name='root_mean_squared_error',
    dtype=None
)
```

Creates a `Mean` instance.


#### Args:


* <b>`name`</b>: (Optional) string name of the metric instance.
* <b>`dtype`</b>: (Optional) data type of the metric result.

<h2 id="__new__"><code>__new__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/metrics.py">View source</a>

``` python
__new__(
    cls,
    *args,
    **kwargs
)
```

Create and return a new object.  See help(type) for accurate signature.




## Methods

<h3 id="reset_states"><code>reset_states</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/metrics.py">View source</a>

``` python
reset_states()
```

Resets all of the metric state variables.

This function is called between epochs/steps,
when a metric is evaluated during training.

<h3 id="result"><code>result</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/metrics.py">View source</a>

``` python
result()
```

Computes and returns the metric value tensor.

Result computation is an idempotent operation that simply calculates the
metric value using the state variables.

<h3 id="update_state"><code>update_state</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/metrics.py">View source</a>

``` python
update_state(
    y_true,
    y_pred,
    sample_weight=None
)
```

Accumulates root mean squared error statistics.


#### Args:


* <b>`y_true`</b>: The ground truth values.
* <b>`y_pred`</b>: The predicted values.
* <b>`sample_weight`</b>: Optional weighting of each example. Defaults to 1. Can be a
  `Tensor` whose rank is either 0, or the same rank as `y_true`, and must
  be broadcastable to `y_true`.


#### Returns:

Update op.






## Compat aliases

* `tf.compat.v1.keras.metrics.RootMeanSquaredError`
* `tf.compat.v2.keras.metrics.RootMeanSquaredError`
* `tf.compat.v2.metrics.RootMeanSquaredError`

