<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.config.PhysicalDevice" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="name"/>
<meta itemprop="property" content="device_type"/>
<meta itemprop="property" content="__new__"/>
</div>

# tf.config.PhysicalDevice

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/eager/context.py">View source</a>



## Class `PhysicalDevice`

Abstraction for a locally visible physical device.



<!-- Placeholder for "Used in" -->

TensorFlow can utilize various devices such as the CPU or multiple GPUs
for computation. Before initializing a local device for use, the user can
customize certain properties of the device such as it's visibility or memory
configuration.

Once a visible <a href="../../tf/config/PhysicalDevice.md"><code>tf.config.PhysicalDevice</code></a> is initialized one or more
<a href="../../tf/config/LogicalDevice.md"><code>tf.config.LogicalDevice</code></a> objects are created. Use
<a href="../../tf/config/set_visible_devices.md"><code>tf.config.set_visible_devices</code></a> to configure the visibility of a physical
device and <a href="../../tf/config/set_logical_device_configuration.md"><code>tf.config.set_logical_device_configuration</code></a> to configure multiple
<a href="../../tf/config/LogicalDevice.md"><code>tf.config.LogicalDevice</code></a> objects for a <a href="../../tf/config/PhysicalDevice.md"><code>tf.config.PhysicalDevice</code></a>. This is
useful when separation between models is needed or to simulate a multi-device
environment.

#### Fields:


* <b>`name`</b>: Unique identifier for device.
* <b>`device_type`</b>: String declaring the type of device such as "CPU" or "GPU".

<h2 id="__new__"><code>__new__</code></h2>

``` python
__new__(
    _cls,
    name,
    device_type
)
```

Create new instance of PhysicalDevice(name, device_type)




## Properties

<h3 id="name"><code>name</code></h3>




<h3 id="device_type"><code>device_type</code></h3>








## Compat aliases

* `tf.compat.v1.config.PhysicalDevice`
* `tf.compat.v2.config.PhysicalDevice`

