<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.config.LogicalDeviceConfiguration" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="memory_limit"/>
<meta itemprop="property" content="__new__"/>
</div>

# tf.config.LogicalDeviceConfiguration

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/eager/context.py">View source</a>



## Class `LogicalDeviceConfiguration`

Configuration class for a logical devices.



**Aliases**: `tf.config.experimental.VirtualDeviceConfiguration`

<!-- Placeholder for "Used in" -->

The class specifies the parameters to configure a <a href="../../tf/config/PhysicalDevice.md"><code>tf.config.PhysicalDevice</code></a>
as it is initialized to a <a href="../../tf/config/LogicalDevice.md"><code>tf.config.LogicalDevice</code></a> during runtime
initialization. Not all fields are valid for all device types.

See <a href="../../tf/config/get_logical_device_configuration.md"><code>tf.config.get_logical_device_configuration</code></a> and
<a href="../../tf/config/set_logical_device_configuration.md"><code>tf.config.set_logical_device_configuration</code></a> for usage examples.

#### Fields:


* <b>`memory_limit`</b>: (optional) Maximum memory (in MB) to allocate on the virtual
  device. Currently only supported for GPUs.

<h2 id="__new__"><code>__new__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/eager/context.py">View source</a>

``` python
@staticmethod
__new__(
    cls,
    memory_limit=None
)
```

Create new instance of LogicalDeviceConfiguration(memory_limit,)




## Properties

<h3 id="memory_limit"><code>memory_limit</code></h3>








## Compat aliases

* `tf.compat.v1.config.LogicalDeviceConfiguration`
* `tf.compat.v1.config.experimental.VirtualDeviceConfiguration`
* `tf.compat.v2.config.LogicalDeviceConfiguration`
* `tf.compat.v2.config.experimental.VirtualDeviceConfiguration`

