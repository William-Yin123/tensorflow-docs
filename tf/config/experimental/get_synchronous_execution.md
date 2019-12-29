<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.config.experimental.get_synchronous_execution" />
<meta itemprop="path" content="Stable" />
</div>

# tf.config.experimental.get_synchronous_execution

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/framework/config.py">View source</a>



Gets whether operations are executed synchronously or asynchronously.

``` python
tf.config.experimental.get_synchronous_execution()
```



<!-- Placeholder for "Used in" -->

TensorFlow can execute operations synchronously or asynchronously. If
asynchronous execution is enabled, operations may return "non-ready" handles.

#### Returns:

Current thread execution mode


## Compat aliases

* `tf.compat.v1.config.experimental.get_synchronous_execution`
* `tf.compat.v2.config.experimental.get_synchronous_execution`

