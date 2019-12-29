<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.ndim" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.ndim

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Returns the number of axes in a tensor, as an integer.

``` python
tf.keras.backend.ndim(x)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`x`</b>: Tensor or variable.


#### Returns:

Integer (scalar), number of axes.



#### Examples:




```

>>> input = tf.keras.backend.placeholder(shape=(2, 4, 5))
>>> val = np.array([[1, 2], [3, 4]])
>>> kvar = tf.keras.backend.variable(value=val)
>>> tf.keras.backend.ndim(input)
3
>>> tf.keras.backend.ndim(kvar)
2

```

## Compat aliases

* `tf.compat.v1.keras.backend.ndim`
* `tf.compat.v2.keras.backend.ndim`

