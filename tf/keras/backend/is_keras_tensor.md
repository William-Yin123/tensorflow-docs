<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.is_keras_tensor" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.is_keras_tensor

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Returns whether `x` is a Keras tensor.

``` python
tf.keras.backend.is_keras_tensor(x)
```



<!-- Placeholder for "Used in" -->

A "Keras tensor" is a tensor that was returned by a Keras layer,
(`Layer` class) or by `Input`.

#### Arguments:


* <b>`x`</b>: A candidate tensor.


#### Returns:

A boolean: Whether the argument is a Keras tensor.



#### Raises:


* <b>`ValueError`</b>: In case `x` is not a symbolic tensor.


#### Examples:



```
>>> np_var = np.array([1, 2])
>>> # A numpy array is not a symbolic tensor.
>>> tf.keras.backend.is_keras_tensor(np_var)
Traceback (most recent call last):
...
ValueError: Unexpectedly found an instance of type `<class 'numpy.ndarray'>`.
Expected a symbolic tensor instance.
>>> keras_var = tf.keras.backend.variable(np_var)
>>> # A variable created with the keras backend is not a Keras tensor.
>>> tf.keras.backend.is_keras_tensor(keras_var)
False
>>> keras_placeholder = tf.keras.backend.placeholder(shape=(2, 4, 5))
>>> # A placeholder is not a Keras tensor.
>>> tf.keras.backend.is_keras_tensor(keras_placeholder)
False
>>> keras_input = tf.keras.layers.Input([10])
>>> # An Input is a Keras tensor.
>>> tf.keras.backend.is_keras_tensor(keras_input)
True
>>> keras_layer_output = tf.keras.layers.Dense(10)(keras_input)
>>> # Any Keras layer output is a Keras tensor.
>>> tf.keras.backend.is_keras_tensor(keras_layer_output)
True
```

## Compat aliases

* `tf.compat.v1.keras.backend.is_keras_tensor`
* `tf.compat.v2.keras.backend.is_keras_tensor`

