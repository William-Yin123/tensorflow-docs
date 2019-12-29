<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.add_to_collections" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.add_to_collections

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/framework/ops.py">View source</a>



Wrapper for `Graph.add_to_collections()` using the default graph.

``` python
tf.compat.v1.add_to_collections(
    names,
    value
)
```



<!-- Placeholder for "Used in" -->

See <a href="../../../tf/Graph.md#add_to_collections"><code>tf.Graph.add_to_collections</code></a>
for more details.

#### Args:


* <b>`names`</b>: The key for the collections. The `GraphKeys` class contains many
  standard names for collections.
* <b>`value`</b>: The value to add to the collections.

#### Eager Compatibility
Collections are only supported in eager when variables are created inside
an EagerVariableStore (e.g. as part of a layer or template).



