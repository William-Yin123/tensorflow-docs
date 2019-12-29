<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.global_variables_initializer" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.global_variables_initializer

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>



Returns an Op that initializes global variables.

``` python
tf.compat.v1.global_variables_initializer()
```



<!-- Placeholder for "Used in" -->

This is just a shortcut for `variables_initializer(global_variables())`

#### Returns:

An Op that initializes global variables in the graph.


## Compat aliases

* `tf.compat.v1.initializers.global_variables`

