<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.eye" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.eye

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Instantiate an identity matrix and returns it.

``` python
tf.keras.backend.eye(
    size,
    dtype=None,
    name=None
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`size`</b>: Integer, number of rows/columns.
* <b>`dtype`</b>: String, data type of returned Keras variable.
* <b>`name`</b>: String, name of returned Keras variable.


#### Returns:

A Keras variable, an identity matrix.



#### Example:




```

>>> kvar = tf.keras.backend.eye(3)
>>> tf.keras.backend.eval(kvar)
array([[1.,  0.,  0.],
       [0.,  1.,  0.],
       [0.,  0.,  1.]], dtype=float32)

```

## Compat aliases

* `tf.compat.v1.keras.backend.eye`
* `tf.compat.v2.keras.backend.eye`

