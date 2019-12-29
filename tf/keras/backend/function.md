<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.function" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.function

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Instantiates a Keras function.

``` python
tf.keras.backend.function(
    inputs,
    outputs,
    updates=None,
    name=None,
    **kwargs
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`inputs`</b>: List of placeholder tensors.
* <b>`outputs`</b>: List of output tensors.
* <b>`updates`</b>: List of update ops.
* <b>`name`</b>: String, name of function.
* <b>`**kwargs`</b>: Passed to `tf.Session.run`.


#### Returns:

Output values as Numpy arrays.



#### Raises:


* <b>`ValueError`</b>: if invalid kwargs are passed in or if in eager execution.

## Compat aliases

* `tf.compat.v1.keras.backend.function`
* `tf.compat.v2.keras.backend.function`

