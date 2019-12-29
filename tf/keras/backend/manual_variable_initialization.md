<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.manual_variable_initialization" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.manual_variable_initialization

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Sets the manual variable initialization flag.

``` python
tf.keras.backend.manual_variable_initialization(value)
```



<!-- Placeholder for "Used in" -->

This boolean flag determines whether
variables should be initialized
as they are instantiated (default), or if
the user should handle the initialization
(e.g. via <a href="../../../tf/compat/v1/initialize_all_variables.md"><code>tf.compat.v1.initialize_all_variables()</code></a>).

#### Arguments:


* <b>`value`</b>: Python boolean.

## Compat aliases

* `tf.compat.v1.keras.backend.manual_variable_initialization`
* `tf.compat.v2.keras.backend.manual_variable_initialization`

