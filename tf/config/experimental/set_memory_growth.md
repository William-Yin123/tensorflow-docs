<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.config.experimental.set_memory_growth" />
<meta itemprop="path" content="Stable" />
</div>

# tf.config.experimental.set_memory_growth

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/framework/config.py">View source</a>



Set if memory growth should be enabled for a `PhysicalDevice`.

``` python
tf.config.experimental.set_memory_growth(
    device,
    enable
)
```



<!-- Placeholder for "Used in" -->

If memory growth is enabled for a `PhysicalDevice`, the runtime initialization
will not allocate all memory on the device. Memory growth cannot be configured
on a `PhysicalDevice` with virtual devices configured.

#### For example:



```
>>> physical_devices = tf.config.list_physical_devices('GPU')
>>> try:
...   tf.config.experimental.set_memory_growth(physical_devices[0], True)
... except:
...   # Invalid device or cannot modify virtual devices once initialized.
...   pass
```

#### Args:


* <b>`device`</b>: `PhysicalDevice` to configure
* <b>`enable`</b>: (Boolean) Whether to enable or disable memory growth


#### Raises:


* <b>`ValueError`</b>: Invalid `PhysicalDevice` specified.
* <b>`RuntimeError`</b>: Runtime is already initialized.

## Compat aliases

* `tf.compat.v1.config.experimental.set_memory_growth`
* `tf.compat.v2.config.experimental.set_memory_growth`

