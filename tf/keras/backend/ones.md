<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.ones" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.ones

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Instantiates an all-ones variable and returns it.

``` python
tf.keras.backend.ones(
    shape,
    dtype=None,
    name=None
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`shape`</b>: Tuple of integers, shape of returned Keras variable.
* <b>`dtype`</b>: String, data type of returned Keras variable.
* <b>`name`</b>: String, name of returned Keras variable.


#### Returns:

A Keras variable, filled with `1.0`.
Note that if `shape` was symbolic, we cannot return a variable,
and will return a dynamically-shaped tensor instead.



#### Example:




```

>>> kvar = tf.keras.backend.ones((3,4))
>>> tf.keras.backend.eval(kvar)
array([[1.,  1.,  1.,  1.],
       [1.,  1.,  1.,  1.],
       [1.,  1.,  1.,  1.]], dtype=float32)

```

## Compat aliases

* `tf.compat.v1.keras.backend.ones`
* `tf.compat.v2.keras.backend.ones`

