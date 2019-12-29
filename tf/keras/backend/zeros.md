<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.zeros" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.zeros

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Instantiates an all-zeros variable and returns it.

``` python
tf.keras.backend.zeros(
    shape,
    dtype=None,
    name=None
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`shape`</b>: Tuple or list of integers, shape of returned Keras variable
* <b>`dtype`</b>: data type of returned Keras variable
* <b>`name`</b>: name of returned Keras variable


#### Returns:

A variable (including Keras metadata), filled with `0.0`.
Note that if `shape` was symbolic, we cannot return a variable,
and will return a dynamically-shaped tensor instead.



#### Example:



```
>>> kvar = tf.keras.backend.zeros((3,4))
>>> tf.keras.backend.eval(kvar)
array([[0.,  0.,  0.,  0.],
       [0.,  0.,  0.,  0.],
       [0.,  0.,  0.,  0.]], dtype=float32)
>>> A = tf.constant([1,2,3])
>>> kvar2 = tf.keras.backend.zeros(A.shape) # [0., 0., 0.]
>>> tf.keras.backend.eval(kvar2)
array([0., 0., 0.], dtype=float32)
>>> kvar3 = tf.keras.backend.zeros(A.shape,dtype=tf.int32)
>>> tf.keras.backend.eval(kvar3)
array([0, 0, 0], dtype=int32)
>>> kvar4 = tf.keras.backend.zeros([2,3])
>>> tf.keras.backend.eval(kvar4)
array([[0., 0., 0.],
       [0., 0., 0.]], dtype=float32)
```

## Compat aliases

* `tf.compat.v1.keras.backend.zeros`
* `tf.compat.v2.keras.backend.zeros`

