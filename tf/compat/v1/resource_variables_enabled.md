<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.resource_variables_enabled" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.resource_variables_enabled

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variable_scope.py">View source</a>



Returns `True` if resource variables are enabled.

``` python
tf.compat.v1.resource_variables_enabled()
```



<!-- Placeholder for "Used in" -->

Resource variables are improved versions of TensorFlow variables with a
well-defined memory model. Accessing a resource variable reads its value, and
all ops which access a specific read value of the variable are guaranteed to
see the same value for that tensor. Writes which happen after a read (by
having a control or data dependency on the read) are guaranteed not to affect
the value of the read tensor, and similarly writes which happen before a read
are guaranteed to affect the value. No guarantees are made about unordered
read/write pairs.

Calling tf.enable_resource_variables() lets you opt-in to this TensorFlow 2.0
feature.

