<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.train.create_global_step" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.train.create_global_step

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/training/training_util.py">View source</a>



Create global step tensor in graph.

``` python
tf.compat.v1.train.create_global_step(graph=None)
```



<!-- Placeholder for "Used in" -->


#### Args:


* <b>`graph`</b>: The graph in which to create the global step tensor. If missing, use
  default graph.


#### Returns:

Global step tensor.



#### Raises:


* <b>`ValueError`</b>: if global step tensor is already defined.

