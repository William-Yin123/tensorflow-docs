<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.container" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.container

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/framework/ops.py">View source</a>



Wrapper for `Graph.container()` using the default graph.

``` python
tf.compat.v1.container(container_name)
```



<!-- Placeholder for "Used in" -->


#### Args:


* <b>`container_name`</b>: The container string to use in the context.


#### Returns:

A context manager that specifies the default container to use for newly
created stateful ops.


