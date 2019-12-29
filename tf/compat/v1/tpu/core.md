<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.tpu.core" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.tpu.core

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/tpu/tpu.py">View source</a>



Returns the device name for a core in a replicated TPU computation.

``` python
tf.compat.v1.tpu.core(num)
```



<!-- Placeholder for "Used in" -->


#### Args:


* <b>`num`</b>: the virtual core number within each replica to which operators should
be assigned.

#### Returns:

A device name, suitable for passing to <a href="../../../../tf/device.md"><code>tf.device()</code></a>.


