<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.int_shape" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.int_shape

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Returns the shape of tensor or variable as a tuple of int or None entries.

``` python
tf.keras.backend.int_shape(x)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`x`</b>: Tensor or variable.


#### Returns:

A tuple of integers (or None entries).



#### Examples:



```
>>> input = tf.keras.backend.placeholder(shape=(2, 4, 5))
>>> tf.keras.backend.int_shape(input)
(2, 4, 5)
>>> val = np.array([[1, 2], [3, 4]])
>>> kvar = tf.keras.backend.variable(value=val)
>>> tf.keras.backend.int_shape(kvar)
(2, 2)
```

## Compat aliases

* `tf.compat.v1.keras.backend.int_shape`
* `tf.compat.v2.keras.backend.int_shape`

