<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.config.LogicalDevice" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="name"/>
<meta itemprop="property" content="device_type"/>
<meta itemprop="property" content="__new__"/>
</div>

# tf.config.LogicalDevice

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/eager/context.py">View source</a>



## Class `LogicalDevice`

Abstraction for a logical device initialized by the runtime.



<!-- Placeholder for "Used in" -->

A <a href="../../tf/config/LogicalDevice.md"><code>tf.config.LogicalDevice</code></a> corresponds to an initialized logical device on a
<a href="../../tf/config/PhysicalDevice.md"><code>tf.config.PhysicalDevice</code></a> or a remote device visible to the cluster. Tensors
and operations can be placed on a specific logical device by calling
<a href="../../tf/device.md"><code>tf.device</code></a> with a specified <a href="../../tf/config/LogicalDevice.md"><code>tf.config.LogicalDevice</code></a>.

#### Fields:


* <b>`name`</b>: The fully qualified name of the device. Can be used for Op or function
  placement.
* <b>`device_type`</b>: String declaring the type of device such as "CPU" or "GPU".

<h2 id="__new__"><code>__new__</code></h2>

``` python
__new__(
    _cls,
    name,
    device_type
)
```

Create new instance of LogicalDevice(name, device_type)




## Properties

<h3 id="name"><code>name</code></h3>




<h3 id="device_type"><code>device_type</code></h3>








## Compat aliases

* `tf.compat.v1.config.LogicalDevice`
* `tf.compat.v2.config.LogicalDevice`

