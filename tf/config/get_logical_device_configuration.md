<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.config.get_logical_device_configuration" />
<meta itemprop="path" content="Stable" />
</div>

# tf.config.get_logical_device_configuration

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/framework/config.py">View source</a>



Get the virtual device configuration for a <a href="../../tf/config/PhysicalDevice.md"><code>tf.config.PhysicalDevice</code></a>.

**Aliases**: `tf.config.experimental.get_virtual_device_configuration`

``` python
tf.config.get_logical_device_configuration(device)
```



<!-- Placeholder for "Used in" -->

Returns the list of <a href="../../tf/config/LogicalDeviceConfiguration.md"><code>tf.config.LogicalDeviceConfiguration</code></a>
objects previously configured by a call to
<a href="../../tf/config/set_logical_device_configuration.md"><code>tf.config.set_logical_device_configuration</code></a>.

#### For example:



```
>>> physical_devices = tf.config.list_physical_devices('CPU')
>>> assert len(physical_devices) == 1, "No CPUs found"
>>> configs = tf.config.get_logical_device_configuration(
...   physical_devices[0])
>>> try:
...   assert configs is None
...   tf.config.set_logical_device_configuration(
...     physical_devices[0],
...     [tf.config.LogicalDeviceConfiguration(),
...      tf.config.LogicalDeviceConfiguration()])
...   configs = tf.config.get_logical_device_configuration(
...     physical_devices[0])
...   assert len(configs) == 2
... except:
...   # Cannot modify virtual devices once initialized.
...   pass
```

#### Args:


* <b>`device`</b>: `PhysicalDevice` to query


#### Returns:

List of <a href="../../tf/config/LogicalDeviceConfiguration.md"><code>tf.config.LogicalDeviceConfiguration</code></a> objects or
`None` if no virtual device configuration has been set for this physical
device.


## Compat aliases

* `tf.compat.v1.config.experimental.get_virtual_device_configuration`
* `tf.compat.v1.config.get_logical_device_configuration`
* `tf.compat.v2.config.experimental.get_virtual_device_configuration`
* `tf.compat.v2.config.get_logical_device_configuration`

