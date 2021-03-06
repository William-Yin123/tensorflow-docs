<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.data.experimental.StatsAggregator" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
</div>

# tf.data.experimental.StatsAggregator

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/data/experimental/ops/stats_aggregator.py">View source</a>



## Class `StatsAggregator`

A stateful resource that aggregates statistics from one or more iterators.



<!-- Placeholder for "Used in" -->

To record statistics, use one of the custom transformation functions defined
in this module when defining your <a href="../../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a>. All statistics will be
aggregated by the `StatsAggregator` that is associated with a particular
iterator (see below). For example, to record the latency of producing each
element by iterating over a dataset:

```python
dataset = ...
dataset = dataset.apply(tf.data.experimental.latency_stats("total_bytes"))
```

To associate a `StatsAggregator` with a <a href="../../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a> object, use
the following pattern:

```python
aggregator = tf.data.experimental.StatsAggregator()
dataset = ...

# Apply `StatsOptions` to associate `dataset` with `aggregator`.
options = tf.data.Options()
options.experimental_stats.aggregator = aggregator
dataset = dataset.with_options(options)
```

Note: This interface is experimental and expected to change. In particular,
we expect to add other implementations of `StatsAggregator` that provide
different ways of exporting statistics, and add more types of statistics.

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/data/experimental/ops/stats_aggregator.py">View source</a>

``` python
__init__()
```

Initialize self.  See help(type(self)) for accurate signature.






## Compat aliases

* `tf.compat.v2.data.experimental.StatsAggregator`

