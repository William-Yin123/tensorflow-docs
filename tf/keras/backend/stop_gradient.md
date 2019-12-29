<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.stop_gradient" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.stop_gradient

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Returns `variables` but with zero gradient w.r.t. every other variable.

``` python
tf.keras.backend.stop_gradient(variables)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`variables`</b>: Tensor or list of tensors to consider constant with respect
  to any other variable.



#### Returns:

A single tensor or a list of tensors (depending on the passed argument)
that has no gradient with respect to any other variable.


## Compat aliases

* `tf.compat.v1.keras.backend.stop_gradient`
* `tf.compat.v2.keras.backend.stop_gradient`

