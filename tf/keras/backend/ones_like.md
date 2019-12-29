<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.ones_like" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.ones_like

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Instantiates an all-ones variable of the same shape as another tensor.

``` python
tf.keras.backend.ones_like(
    x,
    dtype=None,
    name=None
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`x`</b>: Keras variable or tensor.
* <b>`dtype`</b>: String, dtype of returned Keras variable.
     None uses the dtype of x.
* <b>`name`</b>: String, name for the variable to create.


#### Returns:

A Keras variable with the shape of x filled with ones.



#### Example:



```
>>> kvar = tf.keras.backend.variable(np.random.random((2,3)))
>>> kvar_ones = tf.keras.backend.ones_like(kvar)
>>> tf.keras.backend.eval(kvar_ones)
array([[1.,  1.,  1.],
       [1.,  1.,  1.]], dtype=float32)
```

## Compat aliases

* `tf.compat.v1.keras.backend.ones_like`
* `tf.compat.v2.keras.backend.ones_like`

