<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.config.list_logical_devices" />
<meta itemprop="path" content="Stable" />
</div>

# tf.config.list_logical_devices

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/framework/config.py">View source</a>



Return a list of logical devices created by runtime.

**Aliases**: `tf.config.experimental.list_logical_devices`

``` python
tf.config.list_logical_devices(device_type=None)
```



<!-- Placeholder for "Used in" -->

Logical devices may correspond to physical devices or remote devices in the
cluster. Operations and tensors may be placed on these devices by using the
`name` of the <a href="../../tf/config/LogicalDevice.md"><code>tf.config.LogicalDevice</code></a>.

Calling <a href="../../tf/config/list_logical_devices.md"><code>tf.config.list_logical_devices</code></a> triggers the runtime to configure any
<a href="../../tf/config/PhysicalDevice.md"><code>tf.config.PhysicalDevice</code></a> visible to the runtime, thereby preventing
further configuration. To avoid runtime initialization, call
<a href="../../tf/config/list_physical_devices.md"><code>tf.config.list_physical_devices</code></a> instead.

#### For example:



```
>>> logical_devices = tf.config.list_logical_devices('GPU')
>>> if len(logical_devices) > 0:
...   # Allocate on GPU:0
...   with tf.device(logical_devices[0].name):
...     one = tf.constant(1)
...   # Allocate on GPU:1
...   with tf.device(logical_devices[1].name):
...     two = tf.constant(2)
```

#### Args:


* <b>`device_type`</b>: (optional string) Only include devices matching this device
  type. For example "CPU" or "GPU".


#### Returns:

List of initialized `LogicalDevice`s


## Compat aliases

* `tf.compat.v1.config.experimental.list_logical_devices`
* `tf.compat.v1.config.list_logical_devices`
* `tf.compat.v2.config.experimental.list_logical_devices`
* `tf.compat.v2.config.list_logical_devices`

