<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.config.set_soft_device_placement" />
<meta itemprop="path" content="Stable" />
</div>

# tf.config.set_soft_device_placement

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/framework/config.py">View source</a>



Set if soft device placement is enabled.

``` python
tf.config.set_soft_device_placement(enabled)
```



<!-- Placeholder for "Used in" -->

If enabled, an op will be placed on CPU if any of the following are true
  1. there's no GPU implementation for the OP
  2. no GPU devices are known or registered
  3. need to co-locate with reftype input(s) which are from CPU

#### Args:


* <b>`enabled`</b>: Whether to enable soft placement.

## Compat aliases

* `tf.compat.v1.config.set_soft_device_placement`
* `tf.compat.v2.config.set_soft_device_placement`

