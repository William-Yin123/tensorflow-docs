<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.metrics.SparseCategoricalCrossentropy" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="__new__"/>
<meta itemprop="property" content="reset_states"/>
<meta itemprop="property" content="result"/>
<meta itemprop="property" content="update_state"/>
</div>

# tf.keras.metrics.SparseCategoricalCrossentropy

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/metrics.py">View source</a>



## Class `SparseCategoricalCrossentropy`

Computes the crossentropy metric between the labels and predictions.



**Aliases**: `tf.metrics.SparseCategoricalCrossentropy`

<!-- Placeholder for "Used in" -->

Use this crossentropy metric when there are two or more label classes.
We expect labels to be provided as integers. If you want to provide labels
using `one-hot` representation, please use `CategoricalCrossentropy` metric.
There should be `# classes` floating point values per feature for `y_pred`
and a single floating point value per feature for `y_true`.

In the snippet below, there is a single floating point value per example for
`y_true` and `# classes` floating pointing values per example for `y_pred`.
The shape of `y_true` is `[batch_size]` and the shape of `y_pred` is
`[batch_size, num_classes]`.

#### Usage:



```
>>> # y_true = one_hot(y_true) = [[0, 1, 0], [0, 0, 1]]
>>> # logits = log(y_pred)
>>> # softmax = exp(logits) / sum(exp(logits), axis=-1)
>>> # softmax = [[0.05, 0.95, EPSILON], [0.1, 0.8, 0.1]]
>>> # xent = -sum(y * log(softmax), 1)
>>> # log(softmax) = [[-2.9957, -0.0513, -16.1181],
>>> #                [-2.3026, -0.2231, -2.3026]]
>>> # y_true * log(softmax) = [[0, -0.0513, 0], [0, 0, -2.3026]]
>>> # xent = [0.0513, 2.3026]
>>> # Reduced xent = (0.0513 + 2.3026) / 2
>>> m = tf.keras.metrics.SparseCategoricalCrossentropy()
>>> _ = m.update_state([1, 2],
...                    [[0.05, 0.95, 0], [0.1, 0.8, 0.1]])
>>> m.result().numpy()
1.1769392
```

```
>>> m.reset_states()
>>> _ = m.update_state([1, 2],
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
  metrics=[tf.keras.metrics.SparseCategoricalCrossentropy()])
```

#### Args:


* <b>`name`</b>: (Optional) string name of the metric instance.
* <b>`dtype`</b>: (Optional) data type of the metric result.
* <b>`from_logits`</b>: (Optional ) Whether `y_pred` is expected to be a logits tensor.
  By default, we assume that `y_pred` encodes a probability distribution.
* <b>`axis`</b>: (Optional) Defaults to -1. The dimension along which the metric is
  computed.

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/metrics.py">View source</a>

``` python
__init__(
    name='sparse_categorical_crossentropy',
    dtype=None,
    from_logits=False,
    axis=-1
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

* `tf.compat.v1.keras.metrics.SparseCategoricalCrossentropy`
* `tf.compat.v2.keras.metrics.SparseCategoricalCrossentropy`
* `tf.compat.v2.metrics.SparseCategoricalCrossentropy`

