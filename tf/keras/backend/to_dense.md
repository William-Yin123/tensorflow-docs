<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.to_dense" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.to_dense

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Converts a sparse tensor into a dense tensor and returns it.

``` python
tf.keras.backend.to_dense(tensor)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`tensor`</b>: A tensor instance (potentially sparse).


#### Returns:

A dense tensor.



#### Examples:




```

>>> b = tf.keras.backend.placeholder((2, 2), sparse=True)
>>> print(tf.keras.backend.is_sparse(b))
True
>>> c = tf.keras.backend.to_dense(b)
>>> print(tf.keras.backend.is_sparse(c))
False

```

## Compat aliases

* `tf.compat.v1.keras.backend.to_dense`
* `tf.compat.v2.keras.backend.to_dense`

