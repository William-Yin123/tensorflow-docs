<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.flatten" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.flatten

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Flatten a tensor.

``` python
tf.keras.backend.flatten(x)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`x`</b>: A tensor or variable.


#### Returns:

A tensor, reshaped into 1-D



#### Example:


```
>>> b = tf.constant([[1, 2], [3, 4]])
>>> b
<tf.Tensor: shape=(2, 2), dtype=int32, numpy=
array([[1, 2],
       [3, 4]], dtype=int32)>
>>> tf.keras.backend.flatten(b)
<tf.Tensor: shape=(4,), dtype=int32,
    numpy=array([1, 2, 3, 4], dtype=int32)>
```


## Compat aliases

* `tf.compat.v1.keras.backend.flatten`
* `tf.compat.v2.keras.backend.flatten`

