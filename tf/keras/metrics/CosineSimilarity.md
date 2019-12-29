<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.metrics.CosineSimilarity" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="__new__"/>
<meta itemprop="property" content="reset_states"/>
<meta itemprop="property" content="result"/>
<meta itemprop="property" content="update_state"/>
</div>

# tf.keras.metrics.CosineSimilarity

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/metrics.py">View source</a>



## Class `CosineSimilarity`

Computes the cosine similarity between the labels and predictions.



**Aliases**: `tf.metrics.CosineSimilarity`

<!-- Placeholder for "Used in" -->

cosine similarity = (a . b) / ||a|| ||b||
[Cosine Similarity](https://en.wikipedia.org/wiki/Cosine_similarity)

This metric keeps the average cosine similarity between `predictions` and
`labels` over a stream of data.

#### Usage:



```
>>> # l2_norm(y_true) = [[0., 1.], [1./1.414], 1./1.414]]]
>>> # l2_norm(y_pred) = [[1., 0.], [1./1.414], 1./1.414]]]
>>> # l2_norm(y_true) . l2_norm(y_pred) = [[0., 0.], [0.5, 0.5]]
>>> # result = mean(sum(l2_norm(y_true) . l2_norm(y_pred), axis=1))
>>> #        = ((0. + 0.) +  (0.5 + 0.5)) / 2
>>> m = tf.keras.metrics.CosineSimilarity(axis=1)
>>> _ = m.update_state([[0., 1.], [1., 1.]], [[1., 0.], [1., 1.]])
>>> m.result().numpy()
0.49999997
```

```
>>> m.reset_states()
>>> _ = m.update_state([[0., 1.], [1., 1.]], [[1., 0.], [1., 1.]],
...                    sample_weight=[0.3, 0.7])
>>> m.result().numpy()
0.6999999
```

Usage with tf.keras API:

```python
model = tf.keras.Model(inputs, outputs)
model.compile(
    'sgd',
    loss='mse',
    metrics=[tf.keras.metrics.CosineSimilarity(axis=1)])
```

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/metrics.py">View source</a>

``` python
__init__(
    name='cosine_similarity',
    dtype=None,
    axis=-1
)
```

Creates a `CosineSimilarity` instance.


#### Args:


* <b>`name`</b>: (Optional) string name of the metric instance.
* <b>`dtype`</b>: (Optional) data type of the metric result.
* <b>`axis`</b>: (Optional) Defaults to -1. The dimension along which the cosine
  similarity is computed.

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

* `tf.compat.v1.keras.metrics.CosineSimilarity`
* `tf.compat.v2.keras.metrics.CosineSimilarity`
* `tf.compat.v2.metrics.CosineSimilarity`

