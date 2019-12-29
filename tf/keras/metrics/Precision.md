<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.metrics.Precision" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="__new__"/>
<meta itemprop="property" content="reset_states"/>
<meta itemprop="property" content="result"/>
<meta itemprop="property" content="update_state"/>
</div>

# tf.keras.metrics.Precision

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/metrics.py">View source</a>



## Class `Precision`

Computes the precision of the predictions with respect to the labels.

Inherits From: [`Metric`](../../../tf/keras/metrics/Metric.md)

**Aliases**: `tf.metrics.Precision`

<!-- Placeholder for "Used in" -->

The metric creates two local variables, `true_positives` and `false_positives`
that are used to compute the precision. This value is ultimately returned as
`precision`, an idempotent operation that simply divides `true_positives`
by the sum of `true_positives` and `false_positives`.

If `sample_weight` is `None`, weights default to 1.
Use `sample_weight` of 0 to mask values.

If `top_k` is set, we'll calculate precision as how often on average a class
among the top-k classes with the highest predicted values of a batch entry is
correct and can be found in the label for that entry.

If `class_id` is specified, we calculate precision by considering only the
entries in the batch for which `class_id` is above the threshold and/or in the
top-k highest predictions, and computing the fraction of them for which
`class_id` is indeed a correct label.

#### Usage:



```
>>> m = tf.keras.metrics.Precision()
>>> _ = m.update_state([0, 1, 1, 1], [1, 0, 1, 1])
>>> m.result().numpy()
0.6666667
```

```
>>> m.reset_states()
>>> _ = m.update_state([0, 1, 1, 1], [1, 0, 1, 1], sample_weight=[0, 0, 1, 0])
>>> m.result().numpy()
1.0
```

Usage with tf.keras API:

```python
model = tf.keras.Model(inputs, outputs)
model.compile('sgd', loss='mse', metrics=[tf.keras.metrics.Precision()])
```

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/metrics.py">View source</a>

``` python
__init__(
    thresholds=None,
    top_k=None,
    class_id=None,
    name=None,
    dtype=None
)
```

Creates a `Precision` instance.


#### Args:


* <b>`thresholds`</b>: (Optional) A float value or a python list/tuple of float
  threshold values in [0, 1]. A threshold is compared with prediction
  values to determine the truth value of predictions (i.e., above the
  threshold is `true`, below is `false`). One metric value is generated
  for each threshold value. If neither thresholds nor top_k are set, the
  default is to calculate precision with `thresholds=0.5`.
* <b>`top_k`</b>: (Optional) Unset by default. An int value specifying the top-k
  predictions to consider when calculating precision.
* <b>`class_id`</b>: (Optional) Integer class ID for which we want binary metrics.
  This must be in the half-open interval `[0, num_classes)`, where
  `num_classes` is the last dimension of predictions.
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

Accumulates true positive and false positive statistics.


#### Args:


* <b>`y_true`</b>: The ground truth values, with the same dimensions as `y_pred`.
  Will be cast to `bool`.
* <b>`y_pred`</b>: The predicted values. Each element must be in the range `[0, 1]`.
* <b>`sample_weight`</b>: Optional weighting of each example. Defaults to 1. Can be a
  `Tensor` whose rank is either 0, or the same rank as `y_true`, and must
  be broadcastable to `y_true`.


#### Returns:

Update op.






## Compat aliases

* `tf.compat.v1.keras.metrics.Precision`
* `tf.compat.v2.keras.metrics.Precision`
* `tf.compat.v2.metrics.Precision`

