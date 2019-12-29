<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.metrics.CategoricalCrossentropy" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="__new__"/>
<meta itemprop="property" content="reset_states"/>
<meta itemprop="property" content="result"/>
<meta itemprop="property" content="update_state"/>
</div>

# tf.keras.metrics.CategoricalCrossentropy

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/metrics.py">View source</a>



## Class `CategoricalCrossentropy`

Computes the crossentropy metric between the labels and predictions.



**Aliases**: `tf.metrics.CategoricalCrossentropy`

<!-- Placeholder for "Used in" -->

This is the crossentropy metric class to be used when there are multiple
label classes (2 or more). Here we assume that labels are given as a `one_hot`
representation. eg., When labels values are [2, 0, 1],
 `y_true` = [[0, 0, 1], [1, 0, 0], [0, 1, 0]].

#### Usage:



```
>>> # EPSILON = 1e-7, y = y_true, y` = y_pred
>>> # y` = clip_ops.clip_by_value(output, EPSILON, 1. - EPSILON)
>>> # y` = [[0.05, 0.95, EPSILON], [0.1, 0.8, 0.1]]
>>> # xent = -sum(y * log(y'), axis = -1)
>>> #      = -((log 0.95), (log 0.1))
>>> #      = [0.051, 2.302]
>>> # Reduced xent = (0.051 + 2.302) / 2
>>> m = tf.keras.metrics.CategoricalCrossentropy()
>>> _ = m.update_state([[0, 1, 0], [0, 0, 1]],
...                    [[0.05, 0.95, 0], [0.1, 0.8, 0.1]])
>>> m.result().numpy()
1.1769392
```

```
>>> m.reset_states()
>>> _ = m.update_state([[0, 1, 0], [0, 0, 1]],
...                    [[0.05, 0.95, 0], [0.1, 0.8, 0.1]],
...                    sample_weight=tf.constant([0.3, 0.7]))
>>> m.result().numpy()
1.6271976
```

Usage with tf.keras API:

```python
model = tf.keras.Model(inputs, outputs)
model.compile(
  'sgd',
  loss='mse',
  metrics=[tf.keras.metrics.CategoricalCrossentropy()])
```

#### Args:


* <b>`name`</b>: (Optional) string name of the metric instance.
* <b>`dtype`</b>: (Optional) data type of the metric result.
* <b>`from_logits`</b>: (Optional ) Whether `y_pred` is expected to be a logits tensor.
  By default, we assume that `y_pred` encodes a probability distribution.
* <b>`label_smoothing`</b>: Float in [0, 1]. When > 0, label values are smoothed,
  meaning the confidence on label values are relaxed. e.g.
  `label_smoothing=0.2` means that we will use a value of `0.1` for label
  `0` and `0.9` for label `1`"

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/metrics.py">View source</a>

``` python
__init__(
    name='categorical_crossentropy',
    dtype=None,
    from_logits=False,
    label_smoothing=0
)
```

Creates a `MeanMetricWrapper` instance.


#### Args:


* <b>`fn`</b>: The metric function to wrap, with signature
  `fn(y_true, y_pred, **kwargs)`.
* <b>`name`</b>: (Optional) string name of the metric instance.
* <b>`dtype`</b>: (Optional) data type of the metric result.
* <b>`**kwargs`</b>: The keyword arguments that are passed on to `fn`.

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

Accumulates metric statistics.

`y_true` and `y_pred` should have the same shape.

#### Args:


* <b>`y_true`</b>: Ground truth values. shape = `[batch_size, d0, .. dN]`.
* <b>`y_pred`</b>: The predicted values. shape = `[batch_size, d0, .. dN]`.
* <b>`sample_weight`</b>: Optional `sample_weight` acts as a
  coefficient for the metric. If a scalar is provided, then the metric is
  simply scaled by the given value. If `sample_weight` is a tensor of size
  `[batch_size]`, then the metric for each sample of the batch is rescaled
  by the corresponding element in the `sample_weight` vector. If the shape
  of `sample_weight` is `[batch_size, d0, .. dN-1]` (or can be broadcasted
  to this shape), then each metric element of `y_pred` is scaled by the
  corresponding value of `sample_weight`. (Note on `dN-1`: all metric
  functions reduce by 1 dimension, usually the last axis (-1)).


#### Returns:

Update op.






## Compat aliases

* `tf.compat.v1.keras.metrics.CategoricalCrossentropy`
* `tf.compat.v2.keras.metrics.CategoricalCrossentropy`
* `tf.compat.v2.metrics.CategoricalCrossentropy`

