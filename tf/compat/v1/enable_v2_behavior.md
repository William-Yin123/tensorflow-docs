<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.enable_v2_behavior" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.enable_v2_behavior

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/compat/v2_compat.py">View source</a>



Enables TensorFlow 2.x behaviors.

``` python
tf.compat.v1.enable_v2_behavior()
```



<!-- Placeholder for "Used in" -->

This function can be called at the beginning of the program (before `Tensors`,
`Graphs` or other structures have been created, and before devices have been
initialized. It switches all global behaviors that are different between
TensorFlow 1.x and 2.x to behave as intended for 2.x.

This function is called in the main TensorFlow `__init__.py` file, user should
not need to call it, except during complex migrations.

## Compat aliases

* `tf.compat.v2.enable_v2_behavior`

