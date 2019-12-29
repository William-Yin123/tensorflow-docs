<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.data.experimental.cardinality" />
<meta itemprop="path" content="Stable" />
</div>

# tf.data.experimental.cardinality

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/data/experimental/ops/cardinality.py">View source</a>



Returns the cardinality of `dataset`, if known.

``` python
tf.data.experimental.cardinality(dataset)
```



<!-- Placeholder for "Used in" -->

The operation returns the cardinality of `dataset`. The operation may return
<a href="../../../tf/data/experimental.md#INFINITE_CARDINALITY"><code>tf.data.experimental.INFINITE_CARDINALITY</code></a> if `dataset` contains an infinite
number of elements or <a href="../../../tf/data/experimental.md#UNKNOWN_CARDINALITY"><code>tf.data.experimental.UNKNOWN_CARDINALITY</code></a> if the
analysis fails to determine the number of elements in `dataset` (e.g. when the
dataset source is a file).

#### Args:


* <b>`dataset`</b>: A <a href="../../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a> for which to determine cardinality.


#### Returns:

A scalar <a href="../../../tf.md#int64"><code>tf.int64</code></a> `Tensor` representing the cardinality of `dataset`. If
the cardinality is infinite or unknown, the operation returns the named
constant `INFINITE_CARDINALITY` and `UNKNOWN_CARDINALITY` respectively.


## Compat aliases

* `tf.compat.v1.data.experimental.cardinality`
* `tf.compat.v2.data.experimental.cardinality`

