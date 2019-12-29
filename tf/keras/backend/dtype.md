<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.dtype" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.dtype

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Returns the dtype of a Keras tensor or variable, as a string.

``` python
tf.keras.backend.dtype(x)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`x`</b>: Tensor or variable.


#### Returns:

String, dtype of `x`.



#### Examples:



```
>>> tf.keras.backend.dtype(tf.keras.backend.placeholder(shape=(2,4,5)))
'float32'
>>> tf.keras.backend.dtype(tf.keras.backend.placeholder(shape=(2,4,5),
...                                                     dtype='float32'))
'float32'
>>> tf.keras.backend.dtype(tf.keras.backend.placeholder(shape=(2,4,5),
...                                                     dtype='float64'))
'float64'
>>> kvar = tf.keras.backend.variable(np.array([[1, 2], [3, 4]]))
>>> tf.keras.backend.dtype(kvar)
'float32'
>>> kvar = tf.keras.backend.variable(np.array([[1, 2], [3, 4]]),
...                                  dtype='float32')
>>> tf.keras.backend.dtype(kvar)
'float32'
```

## Compat aliases

* `tf.compat.v1.keras.backend.dtype`
* `tf.compat.v2.keras.backend.dtype`

