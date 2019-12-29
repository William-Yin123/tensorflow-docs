<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.random_uniform_variable" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.random_uniform_variable

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Instantiates a variable with values drawn from a uniform distribution.

``` python
tf.keras.backend.random_uniform_variable(
    shape,
    low,
    high,
    dtype=None,
    name=None,
    seed=None
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`shape`</b>: Tuple of integers, shape of returned Keras variable.
* <b>`low`</b>: Float, lower boundary of the output interval.
* <b>`high`</b>: Float, upper boundary of the output interval.
* <b>`dtype`</b>: String, dtype of returned Keras variable.
* <b>`name`</b>: String, name of returned Keras variable.
* <b>`seed`</b>: Integer, random seed.


#### Returns:

A Keras variable, filled with drawn samples.



#### Example:



# TensorFlow example
>>> kvar = tf.keras.backend.random_uniform_variable((2,3), 0, 1)
>>> kvar
<tf.Variable 'Variable:0' shape=(2, 3) dtype=float32, numpy=...,
dtype=float32)>

## Compat aliases

* `tf.compat.v1.keras.backend.random_uniform_variable`
* `tf.compat.v2.keras.backend.random_uniform_variable`

