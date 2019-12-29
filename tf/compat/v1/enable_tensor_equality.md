<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.enable_tensor_equality" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.enable_tensor_equality

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/framework/ops.py">View source</a>



Compare Tensors with element-wise comparison and thus be unhashable.

``` python
tf.compat.v1.enable_tensor_equality()
```



<!-- Placeholder for "Used in" -->

Comparing tensors with element-wise allows comparisons such as
tf.Variable(1.0) == 1.0. Element-wise equality implies that tensors are
unhashable. Thus tensors can no longer be directly used in sets or as a key in
a dictionary.

