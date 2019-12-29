<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.config.list_physical_devices" />
<meta itemprop="path" content="Stable" />
</div>

# tf.config.list_physical_devices

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/framework/config.py">View source</a>



Return a list of physical devices visible to the host runtime.

**Aliases**: `tf.config.experimental.list_physical_devices`

``` python
tf.config.list_physical_devices(device_type=None)
```



<!-- Placeholder for "Used in" -->

Physical devices are hardware devices present on the host machine. By default
all discovered CPU and GPU devices are considered visible.

This API allows querying the physical hardware resources prior to runtime
initialization. Thus, giving an opportunity to call any additional
configuration APIs. This is in contrast to <a href="../../tf/config/list_logical_devices.md"><code>tf.config.list_logical_devices</code></a>,
which triggers runtime initialization in order to list the configured devices.

The following example lists the number of visible GPUs on the host.

```
>>> physical_devices = tf.config.list_physical_devices('GPU')
>>> print("Num GPUs:", len(physical_devices))
Num GPUs: ...
```

However, the number of GPUs available to the runtime may change during runtime
initialization due to marking certain devices as not visible or configuring
multiple logical devices.

#### Args:


* <b>`device_type`</b>: (optional string) Only include devices matching this device
  type. For example "CPU" or "GPU".


#### Returns:

List of discovered <a href="../../tf/config/PhysicalDevice.md"><code>tf.config.PhysicalDevice</code></a> objects


## Compat aliases

* `tf.compat.v1.config.experimental.list_physical_devices`
* `tf.compat.v1.config.list_physical_devices`
* `tf.compat.v2.config.experimental.list_physical_devices`
* `tf.compat.v2.config.list_physical_devices`

