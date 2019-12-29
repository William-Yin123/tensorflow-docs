<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.permute_dimensions" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.permute_dimensions

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Permutes axes in a tensor.

``` python
tf.keras.backend.permute_dimensions(
    x,
    pattern
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`x`</b>: Tensor or variable.
* <b>`pattern`</b>: A tuple of
    dimension indices, e.g. `(0, 2, 1)`.


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
>>> tf.keras.backend.permute_dimensions(a, pattern=(1, 0))
<tf.Tensor: shape=(3, 4), dtype=int32, numpy=
array([[ 1,  4,  7, 10],
       [ 2,  5,  8, 11],
       [ 3,  6,  9, 12]], dtype=int32)>
```


## Compat aliases

* `tf.compat.v1.keras.backend.permute_dimensions`
* `tf.compat.v2.keras.backend.permute_dimensions`

