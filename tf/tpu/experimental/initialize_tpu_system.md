<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.tpu.experimental.initialize_tpu_system" />
<meta itemprop="path" content="Stable" />
</div>

# tf.tpu.experimental.initialize_tpu_system

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/tpu/tpu_strategy_util.py">View source</a>



Initialize the TPU devices.

``` python
tf.tpu.experimental.initialize_tpu_system(cluster_resolver=None)
```



<!-- Placeholder for "Used in" -->


#### Args:


* <b>`cluster_resolver`</b>: A tf.distribute.cluster_resolver.TPUClusterResolver,
    which provides information about the TPU cluster.

#### Returns:

The tf.tpu.Topology object for the topology of the TPU cluster.



#### Raises:


* <b>`RuntimeError`</b>: If no TPU devices found for eager execution or if run in a
    tf.function.

## Compat aliases

* `tf.compat.v1.tpu.experimental.initialize_tpu_system`
* `tf.compat.v2.tpu.experimental.initialize_tpu_system`

