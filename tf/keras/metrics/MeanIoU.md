<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.metrics.MeanIoU" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="__new__"/>
<meta itemprop="property" content="reset_states"/>
<meta itemprop="property" content="result"/>
<meta itemprop="property" content="update_state"/>
</div>

# tf.keras.metrics.MeanIoU

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/metrics.py">View source</a>



## Class `MeanIoU`

Computes the mean Intersection-Over-Union metric.

Inherits From: [`Metric`](../../../tf/keras/metrics/Metric.md)

**Aliases**: `tf.metrics.MeanIoU`

<!-- Placeholder for "Used in" -->

Mean Intersection-Over-Union is a common evaluation metric for semantic image
segmentation, which first computes the IOU for each semantic class and then
computes the average over classes. IOU is defined as follows:
  IOU = true_positive / (true_positive + false_positive + false_negative).
The predictions are accumulated in a confusion matrix, weighted by
`sample_weight` and the metric is then calculated from it.

If `sample_weight` is `None`, weights default to 1.
Use `sample_weight` of 0 to mask values.

#### Usage:



```
>>> # cm = [[1, 1],
>>> #        [1, 1]]
>>> # sum_row = [2, 2], sum_col = [2, 2], true_positives = [1, 1]
>>> # iou = true_positives / (sum_row + sum_col - true_positives))
>>> # result = (1 / (2 + 2 - 1) + 1 / (2 + 2 - 1)) / 2 = 0.33
>>> m = tf.keras.metrics.MeanIoU(num_classes=2)
>>> _ = m.update_state([0, 0, 1, 1], [0, 1, 0, 1])
>>> m.result().numpy()
0.33333334
```

```
>>> m.reset_states()
>>> _ = m.update_state([0, 0, 1, 1], [0, 1, 0, 1],
...                    sample_weight=[0.3, 0.3, 0.3, 0.1])
>>> m.result().numpy()
0.23809525
```

Usage with tf.keras API:

```python
model = tf.keras.Model(inputs, outputs)
model.compile(
  'sgd',
  loss='mse',
  metrics=[tf.keras.metrics.MeanIoU(num_classes=2)])
```

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/metrics.py">View source</a>

``` python
__init__(
    num_classes,
    name=None,
    dtype=None
)
```

Creates a `MeanIoU` instance.


#### Args:


* <b>`num_classes`</b>: The possible number of labels the prediction task can have.
  This value must be provided, since a confusion matrix of dimension =
  [num_classes, num_classes] will be allocated.
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

Compute the mean intersection-over-union via the confusion matrix.


<h3 id="update_state"><code>update_state</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/metrics.py">View source</a>

``` python
update_state(
    y_true,
    y_pred,
    sample_weight=None
)
```

Accumulates the confusion matrix statistics.


#### Args:


* <b>`y_true`</b>: The ground truth values.
* <b>`y_pred`</b>: The predicted values.
* <b>`sample_weight`</b>: Optional weighting of each example. Defaults to 1. Can be a
  `Tensor` whose rank is either 0, or the same rank as `y_true`, and must
  be broadcastable to `y_true`.


#### Returns:

Update op.






## Compat aliases

* `tf.compat.v1.keras.metrics.MeanIoU`
* `tf.compat.v2.keras.metrics.MeanIoU`
* `tf.compat.v2.metrics.MeanIoU`

