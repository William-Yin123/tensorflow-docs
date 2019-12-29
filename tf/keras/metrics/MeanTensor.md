<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.metrics.MeanTensor" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="count"/>
<meta itemprop="property" content="total"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="__new__"/>
<meta itemprop="property" content="reset_states"/>
<meta itemprop="property" content="result"/>
<meta itemprop="property" content="update_state"/>
</div>

# tf.keras.metrics.MeanTensor

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/metrics.py">View source</a>



## Class `MeanTensor`

Computes the element-wise (weighted) mean of the given tensors.

Inherits From: [`Metric`](../../../tf/keras/metrics/Metric.md)

**Aliases**: `tf.metrics.MeanTensor`

<!-- Placeholder for "Used in" -->

`MeanTensor` returns a tensor with the same shape of the input tensors. The
mean value is updated by keeping local variables `total` and `count`. The
`total` tracks the sum of the weighted values, and `count` stores the sum of
the weighted counts.

#### Usage:



```
>>> m = tf.keras.metrics.MeanTensor()
>>> _ = m.update_state([0, 1, 2, 3])
>>> _ = m.update_state([4, 5, 6, 7])
>>> m.result().numpy()
array([2., 3., 4., 5.], dtype=float32)
```

```
>>> _ = m.update_state([12, 10, 8, 6], sample_weight= [0, 0.2, 0.5, 1])
>>> m.result().numpy()
array([2.       , 3.6363635, 4.8      , 5.3333335], dtype=float32)
```

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/metrics.py">View source</a>

``` python
__init__(
    name='mean_tensor',
    dtype=None
)
```

Creates a `MeanTensor` instance.


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




## Properties

<h3 id="count"><code>count</code></h3>




<h3 id="total"><code>total</code></h3>






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
    values,
    sample_weight=None
)
```

Accumulates statistics for computing the element-wise mean.


#### Args:


* <b>`values`</b>: Per-example value.
* <b>`sample_weight`</b>: Optional weighting of each example. Defaults to 1.


#### Returns:

Update op.






## Compat aliases

* `tf.compat.v1.keras.metrics.MeanTensor`
* `tf.compat.v2.keras.metrics.MeanTensor`
* `tf.compat.v2.metrics.MeanTensor`

