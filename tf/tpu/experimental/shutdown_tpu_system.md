<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.tpu.experimental.shutdown_tpu_system" />
<meta itemprop="path" content="Stable" />
</div>

# tf.tpu.experimental.shutdown_tpu_system

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/tpu/tpu_strategy_util.py">View source</a>



Shuts down the TPU devices.

``` python
tf.tpu.experimental.shutdown_tpu_system(cluster_resolver=None)
```



<!-- Placeholder for "Used in" -->

This will clear all caches, even those that are maintained through sequential
calls to tf.tpu.experimental.initialize_tpu_system, such as the compilation
cache.

#### Args:


* <b>`cluster_resolver`</b>: A tf.distribute.cluster_resolver.TPUClusterResolver,
    which provides information about the TPU cluster.


#### Raises:


* <b>`RuntimeError`</b>: If no TPU devices found for eager execution or if run in a
    tf.function.

## Compat aliases

* `tf.compat.v1.tpu.experimental.shutdown_tpu_system`
* `tf.compat.v2.tpu.experimental.shutdown_tpu_system`

