<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.distribute.experimental.CollectiveCommunication" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="AUTO"/>
<meta itemprop="property" content="NCCL"/>
<meta itemprop="property" content="RING"/>
</div>

# tf.distribute.experimental.CollectiveCommunication

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/distribute/cross_device_ops.py">View source</a>



## Class `CollectiveCommunication`

Communication choices for CollectiveOps.



<!-- Placeholder for "Used in" -->

* `AUTO`: Default to runtime's automatic choices.
* `RING`: TensorFlow's ring algorithms for all-reduce and
  all-gather.
* `NCCL`: Use ncclAllReduce for all-reduce, and ring algorithms for
  all-gather.

## Class Members

* `AUTO` <a id="AUTO"></a>
* `NCCL` <a id="NCCL"></a>
* `RING` <a id="RING"></a>


## Compat aliases

* `tf.compat.v1.distribute.experimental.CollectiveCommunication`
* `tf.compat.v2.distribute.experimental.CollectiveCommunication`

