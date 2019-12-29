<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.metrics.TopKCategoricalAccuracy" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="__new__"/>
<meta itemprop="property" content="reset_states"/>
<meta itemprop="property" content="result"/>
<meta itemprop="property" content="update_state"/>
</div>

# tf.keras.metrics.TopKCategoricalAccuracy

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/metrics.py">View source</a>



## Class `TopKCategoricalAccuracy`

Computes how often targets are in the top `K` predictions.



**Aliases**: `tf.metrics.TopKCategoricalAccuracy`

<!-- Placeholder for "Used in" -->


#### Usage:



```
>>> m = tf.keras.metrics.TopKCategoricalAccuracy(k=1)
>>> _ = m.update_state([[0, 0, 1], [0, 1, 0]],
...                    [[0.1, 0.9, 0.8], [0.05, 0.95, 0]])
>>> m.result().numpy()
0.5
```

```
>>> m.reset_states()
>>> _ = m.update_state([[0, 0, 1], [0, 1, 0]],
...                    [[0.1, 0.9, 0.8], [0.05, 0.95, 0]],
...                    sample_weight=[0.7, 0.3])
>>> m.result().numpy()
0.3
```

Usage with tf.keras API:

```python
model = tf.keras.Model(inputs, outputs)
model.compile('sgd', metrics=[tf.keras.metrics.TopKCategoricalAccuracy()])
```

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/metrics.py">View source</a>

``` python
__init__(
    k=5,
    name='top_k_categorical_accuracy',
    dtype=None
)
```

Creates a `TopKCategoricalAccuracy` instance.


#### Args:


* <b>`k`</b>: (Optional) Number of top elements to look at for computing accuracy.
  Defaults to 5.
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

* `tf.compat.v1.keras.metrics.TopKCategoricalAccuracy`
* `tf.compat.v2.keras.metrics.TopKCategoricalAccuracy`
* `tf.compat.v2.metrics.TopKCategoricalAccuracy`

