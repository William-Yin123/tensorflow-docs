<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.batch_get_value" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.batch_get_value

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Returns the value of more than one tensor variable.

``` python
tf.keras.backend.batch_get_value(tensors)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`tensors`</b>: list of ops to run.


#### Returns:

A list of Numpy arrays.



#### Raises:


* <b>`RuntimeError`</b>: If this method is called inside defun.

## Compat aliases

* `tf.compat.v1.keras.backend.batch_get_value`
* `tf.compat.v2.keras.backend.batch_get_value`

