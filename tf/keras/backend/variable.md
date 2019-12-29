<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.variable" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.variable

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Instantiates a variable and returns it.

``` python
tf.keras.backend.variable(
    value,
    dtype=None,
    name=None,
    constraint=None
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`value`</b>: Numpy array, initial value of the tensor.
* <b>`dtype`</b>: Tensor type.
* <b>`name`</b>: Optional name string for the tensor.
* <b>`constraint`</b>: Optional projection function to be
    applied to the variable after an optimizer update.


#### Returns:

A variable instance (with Keras metadata included).



#### Examples:



```
>>> val = np.array([[1, 2], [3, 4]])
>>> kvar = tf.keras.backend.variable(value=val, dtype='float64',
...                                  name='example_var')
>>> tf.keras.backend.dtype(kvar)
'float64'
>>> print(kvar)
<tf.Variable 'example_var:...' shape=(2, 2) dtype=float64, numpy=
  array([[1., 2.],
         [3., 4.]])>
```

## Compat aliases

* `tf.compat.v1.keras.backend.variable`
* `tf.compat.v2.keras.backend.variable`

