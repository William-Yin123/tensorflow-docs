<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.reshape" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.reshape

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Reshapes a tensor to the specified shape.

``` python
tf.keras.backend.reshape(
    x,
    shape
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`x`</b>: Tensor or variable.
* <b>`shape`</b>: Target shape tuple.


#### Returns:

A tensor.



#### Example:


```
>>> a = tf.constant([[1, 2, 3], [4, 5, 6], [7, 8, 9], [10, 11, 12]])
>>> a
<tf.Tensor: shape=(4, 3), dtype=int32, numpy=
array([[ 1,  2,  3],
       [ 4,  5,  6],
       [ 7,  8,  9],
       [10, 11, 12]], dtype=int32)>
>>> tf.keras.backend.reshape(a, shape=(2, 6))
<tf.Tensor: shape=(2, 6), dtype=int32, numpy=
array([[ 1,  2,  3,  4,  5,  6],
       [ 7,  8,  9, 10, 11, 12]], dtype=int32)>
```


## Compat aliases

* `tf.compat.v1.keras.backend.reshape`
* `tf.compat.v2.keras.backend.reshape`

