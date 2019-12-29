<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.get_default_graph" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.get_default_graph

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/framework/ops.py">View source</a>



Returns the default graph for the current thread.

``` python
tf.compat.v1.get_default_graph()
```



<!-- Placeholder for "Used in" -->

The returned graph will be the innermost graph on which a
`Graph.as_default()` context has been entered, or a global default
graph if none has been explicitly created.

NOTE: The default graph is a property of the current thread. If you
create a new thread, and wish to use the default graph in that
thread, you must explicitly add a `with g.as_default():` in that
thread's function.

#### Returns:

The default `Graph` being used in the current thread.


