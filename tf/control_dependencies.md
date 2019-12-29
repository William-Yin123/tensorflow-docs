<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.control_dependencies" />
<meta itemprop="path" content="Stable" />
</div>

# tf.control_dependencies

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/framework/ops.py">View source</a>



Wrapper for <a href="../tf/Graph.md#control_dependencies"><code>Graph.control_dependencies()</code></a> using the default graph.

``` python
tf.control_dependencies(control_inputs)
```



<!-- Placeholder for "Used in" -->

See <a href="../tf/Graph.md#control_dependencies"><code>tf.Graph.control_dependencies</code></a>
for more details.

When eager execution is enabled, any callable object in the `control_inputs`
list will be called.

#### Args:


* <b>`control_inputs`</b>: A list of `Operation` or `Tensor` objects which must be
  executed or computed before running the operations defined in the context.
  Can also be `None` to clear the control dependencies. If eager execution
  is enabled, any callable object in the `control_inputs` list will be
  called.


#### Returns:

A context manager that specifies control dependencies for all
operations constructed within the context.


## Compat aliases

* `tf.compat.v1.control_dependencies`
* `tf.compat.v2.control_dependencies`

