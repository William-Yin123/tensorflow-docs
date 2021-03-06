<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.device" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.device

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/framework/ops.py">View source</a>



Wrapper for `Graph.device()` using the default graph.

``` python
tf.compat.v1.device(device_name_or_function)
```



<!-- Placeholder for "Used in" -->

See <a href="../../../tf/Graph.md#device"><code>tf.Graph.device</code></a> for more details.

#### Args:


* <b>`device_name_or_function`</b>: The device name or function to use in the context.


#### Returns:

A context manager that specifies the default device to use for newly
created ops.



#### Raises:


* <b>`RuntimeError`</b>: If eager execution is enabled and a function is passed in.

