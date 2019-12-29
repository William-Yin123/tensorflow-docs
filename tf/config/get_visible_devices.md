<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.config.get_visible_devices" />
<meta itemprop="path" content="Stable" />
</div>

# tf.config.get_visible_devices

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/framework/config.py">View source</a>



Get the list of visible physical devices.

**Aliases**: `tf.config.experimental.get_visible_devices`

``` python
tf.config.get_visible_devices(device_type=None)
```



<!-- Placeholder for "Used in" -->

Returns the list of `PhysicalDevice`s currently marked as visible to the
runtime. A visible device will have at least one `LogicalDevice` associated
with it once the runtime is initialized.

The following example verifies all visible GPUs have been disabled:

```
>>> physical_devices = tf.config.list_physical_devices('GPU')
>>> try:
...   # Disable all GPUS
...   tf.config.set_visible_devices([], 'GPU')
...   visible_devices = tf.config.get_visible_devices()
...   for device in visible_devices:
...     assert device.device_type != 'GPU'
... except:
...   # Invalid device or cannot modify virtual devices once initialized.
...   pass
```

#### Args:


* <b>`device_type`</b>: (optional string) Only include devices matching this device
  type. For example "CPU" or "GPU".


#### Returns:

List of visible `PhysicalDevice`s


## Compat aliases

* `tf.compat.v1.config.experimental.get_visible_devices`
* `tf.compat.v1.config.get_visible_devices`
* `tf.compat.v2.config.experimental.get_visible_devices`
* `tf.compat.v2.config.get_visible_devices`

