<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.disable_eager_execution" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.disable_eager_execution

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/framework/ops.py">View source</a>



Disables eager execution.

``` python
tf.compat.v1.disable_eager_execution()
```



<!-- Placeholder for "Used in" -->

This function can only be called before any Graphs, Ops, or Tensors have been
created. It can be used at the beginning of the program for complex migration
projects from TensorFlow 1.x to 2.x.

