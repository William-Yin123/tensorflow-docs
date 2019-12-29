<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.is_sparse" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.is_sparse

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Returns whether a tensor is a sparse tensor.

``` python
tf.keras.backend.is_sparse(tensor)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`tensor`</b>: A tensor instance.


#### Returns:

A boolean.



#### Example:




```

>>> a = tf.keras.backend.placeholder((2, 2), sparse=False)
>>> print(tf.keras.backend.is_sparse(a))
False
>>> b = tf.keras.backend.placeholder((2, 2), sparse=True)
>>> print(tf.keras.backend.is_sparse(b))
True

```

## Compat aliases

* `tf.compat.v1.keras.backend.is_sparse`
* `tf.compat.v2.keras.backend.is_sparse`

