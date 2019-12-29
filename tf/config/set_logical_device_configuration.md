<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.config.set_logical_device_configuration" />
<meta itemprop="path" content="Stable" />
</div>

# tf.config.set_logical_device_configuration

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/framework/config.py">View source</a>



Set the logical device configuration for a <a href="../../tf/config/PhysicalDevice.md"><code>tf.config.PhysicalDevice</code></a>.

**Aliases**: `tf.config.experimental.set_virtual_device_configuration`

``` python
tf.config.set_logical_device_configuration(
    device,
    logical_devices
)
```



<!-- Placeholder for "Used in" -->

A visible <a href="../../tf/config/PhysicalDevice.md"><code>tf.config.PhysicalDevice</code></a> will by default have a single
<a href="../../tf/config/LogicalDevice.md"><code>tf.config.LogicalDevice</code></a> associated with it once the runtime is initialized.
Specifying a list of <a href="../../tf/config/LogicalDeviceConfiguration.md"><code>tf.config.LogicalDeviceConfiguration</code></a> objects allows
multiple devices to be created on the same <a href="../../tf/config/PhysicalDevice.md"><code>tf.config.PhysicalDevice</code></a>.

The following example splits the CPU into 2 logical devices:

```
>>> physical_devices = tf.config.list_physical_devices('CPU')
>>> assert len(physical_devices) == 1, "No CPUs found"
>>> # Specify 2 virtual CPUs. Note currently memory limit is not supported.
>>> try:
...   tf.config.set_logical_device_configuration(
...     physical_devices[0],
...     [tf.config.LogicalDeviceConfiguration(),
...      tf.config.LogicalDeviceConfiguration()])
...   logical_devices = tf.config.list_logical_devices('CPU')
...   assert len(logical_devices) == 2
...
...   tf.config.set_logical_device_configuration(
...     physical_devices[0],
...     [tf.config.LogicalDeviceConfiguration(),
...      tf.config.LogicalDeviceConfiguration(),
...      tf.config.LogicalDeviceConfiguration(),
...      tf.config.LogicalDeviceConfiguration()])
... except:
...   # Cannot modify logical devices once initialized.
...   pass
```

The following example splits the GPU into 2 logical devices with 100 MB each:

```
>>> physical_devices = tf.config.list_physical_devices('GPU')
>>> try:
...   tf.config.set_logical_device_configuration(
...     physical_devices[0],
...     [tf.config.LogicalDeviceConfiguration(memory_limit=100),
...      tf.config.LogicalDeviceConfiguration(memory_limit=100)])
...
...   logical_devices = tf.config.list_logical_devices('GPU')
...   assert len(logical_devices) == len(physical_devices) + 1
...
...   tf.config.set_logical_device_configuration(
...     physical_devices[0],
...     [tf.config.LogicalDeviceConfiguration(memory_limit=10),
...      tf.config.LogicalDeviceConfiguration(memory_limit=10)])
... except:
...   # Invalid device or cannot modify logical devices once initialized.
...   pass
```

#### Args:


* <b>`device`</b>: The `PhysicalDevice` to configure.
* <b>`logical_devices`</b>: (optional) List of <a href="../../tf/config/LogicalDeviceConfiguration.md"><code>tf.config.LogicalDeviceConfiguration</code></a>
  objects to allocate for the specified `PhysicalDevice`. If None, the
  default configuration will be used.


#### Raises:


* <b>`ValueError`</b>: If argument validation fails.
* <b>`RuntimeError`</b>: Runtime is already initialized.

## Compat aliases

* `tf.compat.v1.config.experimental.set_virtual_device_configuration`
* `tf.compat.v1.config.set_logical_device_configuration`
* `tf.compat.v2.config.experimental.set_virtual_device_configuration`
* `tf.compat.v2.config.set_logical_device_configuration`

