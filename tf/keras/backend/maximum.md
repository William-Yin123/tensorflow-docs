<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.maximum" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.maximum

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Element-wise maximum of two tensors.

``` python
tf.keras.backend.maximum(
    x,
    y
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`x`</b>: Tensor or variable.
* <b>`y`</b>: Tensor or variable.


#### Returns:

A tensor with the element wise maximum value(s) of `x` and `y`.



#### Examples:



# maximum of two tensors
>>> x = tf.Variable([[1, 2], [3, 4]])
>>> y = tf.Variable([[2, 1], [0, -1]])
>>> m = tf.keras.backend.maximum(x, y)
>>> m
<tf.Tensor: shape=(2, 2), dtype=int32, numpy=
array([[2, 2],
       [3, 4]], dtype=int32)>

## Compat aliases

* `tf.compat.v1.keras.backend.maximum`
* `tf.compat.v2.keras.backend.maximum`

