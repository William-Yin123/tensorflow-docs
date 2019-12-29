<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.dot" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.dot

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Multiplies 2 tensors (and/or variables) and returns a *tensor*.

``` python
tf.keras.backend.dot(
    x,
    y
)
```



<!-- Placeholder for "Used in" -->

When attempting to multiply a nD tensor
with a nD tensor, it reproduces the Theano behavior.
(e.g. `(2, 3) * (4, 3, 5) -> (2, 4, 5)`)

#### Arguments:


* <b>`x`</b>: Tensor or variable.
* <b>`y`</b>: Tensor or variable.


#### Returns:

A tensor, dot product of `x` and `y`.



#### Examples:



# dot product between tensors
>>> x = tf.keras.backend.placeholder(shape=(2, 3))
>>> y = tf.keras.backend.placeholder(shape=(3, 4))
>>> xy = tf.keras.backend.dot(x, y)
>>> xy
<tf.Tensor ... shape=(2, 4) dtype=float32>

# dot product between tensors
>>> x = tf.keras.backend.placeholder(shape=(32, 28, 3))
>>> y = tf.keras.backend.placeholder(shape=(3, 4))
>>> xy = tf.keras.backend.dot(x, y)
>>> xy
<tf.Tensor ... shape=(32, 28, 4) dtype=float32>

# Theano-like behavior example
>>> x = tf.keras.backend.random_uniform_variable(shape=(2, 3), low=0, high=1)
>>> y = tf.keras.backend.ones((4, 3, 5))
>>> xy = tf.keras.backend.dot(x, y)
>>> tf.keras.backend.int_shape(xy)
(2, 4, 5)

## Compat aliases

* `tf.compat.v1.keras.backend.dot`
* `tf.compat.v2.keras.backend.dot`

