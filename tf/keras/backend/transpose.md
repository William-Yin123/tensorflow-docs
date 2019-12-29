<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.transpose" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.transpose

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Transposes a tensor and returns it.

``` python
tf.keras.backend.transpose(x)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`x`</b>: Tensor or variable.


#### Returns:

A tensor.



#### Examples:



```
>>> var = tf.keras.backend.variable([[1, 2, 3], [4, 5, 6]])
>>> tf.keras.backend.eval(var)
array([[1.,  2.,  3.],
       [4.,  5.,  6.]], dtype=float32)
>>> var_transposed = tf.keras.backend.transpose(var)
>>> tf.keras.backend.eval(var_transposed)
array([[1.,  4.],
       [2.,  5.],
       [3.,  6.]], dtype=float32)
>>> input = tf.keras.backend.placeholder((2, 3))
>>> input
<tf.Tensor 'Placeholder_...' shape=(2, 3) dtype=float32>
>>> input_transposed = tf.keras.backend.transpose(input)
>>> input_transposed
<tf.Tensor 'Transpose_...' shape=(3, 2) dtype=float32>
```

## Compat aliases

* `tf.compat.v1.keras.backend.transpose`
* `tf.compat.v2.keras.backend.transpose`

