<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.data.experimental.DistributeOptions" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="auto_shard_policy"/>
<meta itemprop="property" content="num_devices"/>
<meta itemprop="property" content="__eq__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="__ne__"/>
</div>

# tf.data.experimental.DistributeOptions

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/data/experimental/ops/distribute_options.py">View source</a>



## Class `DistributeOptions`

Represents options for distributed data processing.



<!-- Placeholder for "Used in" -->

You can set the distribution options of a dataset through the
`experimental_distribute` property of <a href="../../../tf/data/Options.md"><code>tf.data.Options</code></a>; the property is
an instance of <a href="../../../tf/data/experimental/DistributeOptions.md"><code>tf.data.experimental.DistributeOptions</code></a>.

```python
options = tf.data.Options()
options.experimental_distribute.auto_shard_policy = AutoShardPolicy.OFF
dataset = dataset.with_options(options)
```

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/data/util/options.py">View source</a>

``` python
__init__()
```

Initialize self.  See help(type(self)) for accurate signature.




## Properties

<h3 id="auto_shard_policy"><code>auto_shard_policy</code></h3>

The type of sharding that auto-shard should attempt. If this is set to FILE, then we will attempt to shard by files (each worker will get a set of files to process). If we cannot find a set of files to shard for at least one file per worker, we will error out. When this option is selected, make sure that you have enough files so that each worker gets at least one file. There will be a runtime error thrown if there are insufficient files. If this is set to DATA, then we will shard by elements produced by the dataset, and each worker will process the whole dataset and discard the portion that is not for itself. If this is set to OFF, then we will not autoshard, and each worker will receive a copy of the full dataset. This option is set to AUTO by default, AUTO will attempt to first shard by FILE, and fall back to sharding by DATA if we cannot find a set of files to shard.


<h3 id="num_devices"><code>num_devices</code></h3>

The number of devices attached to this input pipeline. This will be automatically set by MultiDeviceIterator.




## Methods

<h3 id="__eq__"><code>__eq__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/data/util/options.py">View source</a>

``` python
__eq__(other)
```

Return self==value.


<h3 id="__ne__"><code>__ne__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/data/util/options.py">View source</a>

``` python
__ne__(other)
```

Return self!=value.






## Compat aliases

* `tf.compat.v1.data.experimental.DistributeOptions`
* `tf.compat.v2.data.experimental.DistributeOptions`

