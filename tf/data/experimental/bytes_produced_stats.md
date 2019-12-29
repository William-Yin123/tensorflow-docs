<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.data.experimental.bytes_produced_stats" />
<meta itemprop="path" content="Stable" />
</div>

# tf.data.experimental.bytes_produced_stats

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/data/experimental/ops/stats_ops.py">View source</a>



Records the number of bytes produced by each element of the input dataset.

``` python
tf.data.experimental.bytes_produced_stats(tag)
```



<!-- Placeholder for "Used in" -->

To consume the statistics, associate a `StatsAggregator` with the output
dataset.

#### Args:


* <b>`tag`</b>: String. All statistics recorded by the returned transformation will
  be associated with the given `tag`.


#### Returns:

A `Dataset` transformation function, which can be passed to
<a href="../../../tf/data/Dataset.md#apply"><code>tf.data.Dataset.apply</code></a>.


## Compat aliases

* `tf.compat.v1.data.experimental.bytes_produced_stats`
* `tf.compat.v2.data.experimental.bytes_produced_stats`

