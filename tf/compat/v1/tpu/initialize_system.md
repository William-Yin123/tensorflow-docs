<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.tpu.initialize_system" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.tpu.initialize_system

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/tpu/tpu.py">View source</a>



Initializes a distributed TPU system for use with TensorFlow.

``` python
tf.compat.v1.tpu.initialize_system(
    embedding_config=None,
    job=None,
    compilation_failure_closes_chips=True
)
```



<!-- Placeholder for "Used in" -->


#### Args:


* <b>`embedding_config`</b>: If not None, a `TPUEmbeddingConfiguration` proto
  describing the desired configuration of the hardware embedding lookup
  tables. If embedding_config is None, no hardware embeddings can be used.
* <b>`job`</b>: The job (the XXX in TensorFlow device specification /job:XXX) that
  contains the TPU devices that will be initialized. If job=None it is
  assumed there is only one job in the TensorFlow flock, and an error will
  be returned if this assumption does not hold.
* <b>`compilation_failure_closes_chips`</b>: Set the configuration whether
  we want to close TPU chips when there is a compilation failure.

#### Returns:

A serialized `TopologyProto` that describes the TPU system. Note:
  the topology must be evaluated using `Session.run` before it can be used.


