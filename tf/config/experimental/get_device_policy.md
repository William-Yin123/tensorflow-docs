<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.config.experimental.get_device_policy" />
<meta itemprop="path" content="Stable" />
</div>

# tf.config.experimental.get_device_policy

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/framework/config.py">View source</a>



Gets the current device policy.

``` python
tf.config.experimental.get_device_policy()
```



<!-- Placeholder for "Used in" -->

The device policy controls how operations requiring inputs on a specific
device (e.g., on GPU:0) handle inputs on a different device (e.g. GPU:1).

This function only gets the device policy for the current thread. Any
subsequently started thread will again use the default policy.

#### Returns:

Current thread device policy


## Compat aliases

* `tf.compat.v1.config.experimental.get_device_policy`
* `tf.compat.v2.config.experimental.get_device_policy`

