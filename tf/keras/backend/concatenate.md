<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.concatenate" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.concatenate

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Concatenates a list of tensors alongside the specified axis.

``` python
tf.keras.backend.concatenate(
    tensors,
    axis=-1
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`tensors`</b>: list of tensors to concatenate.
* <b>`axis`</b>: concatenation axis.


#### Returns:

A tensor.



#### Example:


```
>>> a = tf.constant([[1, 2, 3], [4, 5, 6], [7, 8, 9]])
>>> b = tf.constant([[10, 20, 30], [40, 50, 60], [70, 80, 90]])
>>> tf.keras.backend.concatenate((a, b), axis=-1)
<tf.Tensor: shape=(3, 6), dtype=int32, numpy=
array([[ 1,  2,  3, 10, 20, 30],
       [ 4,  5,  6, 40, 50, 60],
       [ 7,  8,  9, 70, 80, 90]], dtype=int32)>
```


## Compat aliases

* `tf.compat.v1.keras.backend.concatenate`
* `tf.compat.v2.keras.backend.concatenate`

