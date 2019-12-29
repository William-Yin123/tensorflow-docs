<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.is_variable_initialized" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.is_variable_initialized

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>



Tests if a variable has been initialized.

``` python
tf.compat.v1.is_variable_initialized(variable)
```



<!-- Placeholder for "Used in" -->


#### Args:


* <b>`variable`</b>: A `Variable`.


#### Returns:

Returns a scalar boolean Tensor, `True` if the variable has been
initialized, `False` otherwise.



**NOTE** The output of this function should be used.  If it is not, a warning will be logged or an error may be raised.  To mark the output as used, call its .mark_used() method.

