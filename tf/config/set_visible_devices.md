<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.config.set_visible_devices" />
<meta itemprop="path" content="Stable" />
</div>

# tf.config.set_visible_devices

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/framework/config.py">View source</a>



Set the list of visible devices.

**Aliases**: `tf.config.experimental.set_visible_devices`

``` python
tf.config.set_visible_devices(
    devices,
    device_type=None
)
```



<!-- Placeholder for "Used in" -->

Specifies which `PhysicalDevice` objects are visible to the runtime.
TensorFlow will only allocate memory and place operations on visible
physical devices, as otherwise no `LogicalDevice` will be created on them.
By default all discovered devices are marked as visible.

The following example demonstrates disabling the first GPU on the machine.

```
>>> physical_devices = tf.config.list_physical_devices('GPU')
>>> try:
...   # Disable first GPU
...   tf.config.set_visible_devices(physical_devices[1:], 'GPU')
...   logical_devices = tf.config.list_logical_devices('GPU')
...   # Logical device was not created for first GPU
...   assert len(logical_devices) == len(physical_devices) - 1
... except:
...   # Invalid device or cannot modify virtual devices once initialized.
...   pass
```

#### Args:


* <b>`devices`</b>: List of `PhysicalDevice`s to make visible
* <b>`device_type`</b>: (optional) Only configure devices matching this device type.
  For example "CPU" or "GPU". Other devices will be left unaltered.


#### Raises:


* <b>`ValueError`</b>: If argument validation fails.
* <b>`RuntimeError`</b>: Runtime is already initialized.

## Compat aliases

* `tf.compat.v1.config.experimental.set_visible_devices`
* `tf.compat.v1.config.set_visible_devices`
* `tf.compat.v2.config.experimental.set_visible_devices`
* `tf.compat.v2.config.set_visible_devices`

