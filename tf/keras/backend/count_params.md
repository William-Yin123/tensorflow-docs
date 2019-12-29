<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.count_params" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.count_params

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Returns the static number of elements in a variable or tensor.

``` python
tf.keras.backend.count_params(x)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`x`</b>: Variable or tensor.


#### Returns:

Integer, the number of scalars in `x`.



#### Example:



```
>>> kvar = tf.keras.backend.zeros((2,3))
>>> tf.keras.backend.count_params(kvar)
6
>>> tf.keras.backend.eval(kvar)
array([[0.,  0.,  0.],
       [0.,  0.,  0.]], dtype=float32)
```

## Compat aliases

* `tf.compat.v1.keras.backend.count_params`
* `tf.compat.v2.keras.backend.count_params`

