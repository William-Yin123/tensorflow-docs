<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.shape" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.shape

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Returns the symbolic shape of a tensor or variable.

``` python
tf.keras.backend.shape(x)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`x`</b>: A tensor or variable.


#### Returns:

A symbolic shape (which is itself a tensor).



#### Examples:



```
>>> val = np.array([[1, 2], [3, 4]])
>>> kvar = tf.keras.backend.variable(value=val)
>>> tf.keras.backend.shape(kvar)
<tf.Tensor: shape=(2,), dtype=int32, numpy=array([2, 2], dtype=int32)>
>>> input = tf.keras.backend.placeholder(shape=(2, 4, 5))
>>> tf.keras.backend.shape(input)
<tf.Tensor 'Shape_...' shape=(3,) dtype=int32>
```

## Compat aliases

* `tf.compat.v1.keras.backend.shape`
* `tf.compat.v2.keras.backend.shape`

