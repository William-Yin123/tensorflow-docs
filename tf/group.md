<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.group" />
<meta itemprop="path" content="Stable" />
</div>

# tf.group

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/control_flow_ops.py">View source</a>



Create an op that groups multiple operations.

``` python
tf.group(
    *inputs,
    **kwargs
)
```



<!-- Placeholder for "Used in" -->

When this op finishes, all ops in `inputs` have finished. This op has no
output.

See also <a href="../tf/tuple.md"><code>tf.tuple</code></a> and
<a href="../tf/control_dependencies.md"><code>tf.control_dependencies</code></a>.

#### Args:


* <b>`*inputs`</b>: Zero or more tensors to group.
* <b>`name`</b>: A name for this operation (optional).


#### Returns:

An Operation that executes all its inputs.



#### Raises:


* <b>`ValueError`</b>: If an unknown keyword argument is provided.

## Compat aliases

* `tf.compat.v1.group`
* `tf.compat.v2.group`

