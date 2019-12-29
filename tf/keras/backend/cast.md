<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.cast" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.cast

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Casts a tensor to a different dtype and returns it.

``` python
tf.keras.backend.cast(
    x,
    dtype
)
```



<!-- Placeholder for "Used in" -->

You can cast a Keras variable but it still returns a Keras tensor.

#### Arguments:


* <b>`x`</b>: Keras tensor (or variable).
* <b>`dtype`</b>: String, either (`'float16'`, `'float32'`, or `'float64'`).


#### Returns:

Keras tensor with dtype `dtype`.



#### Examples:

Cast a float32 variable to a float64 tensor


```
>>> input = tf.keras.backend.ones(shape=(1,3))
>>> print(input)
<tf.Variable 'Variable:0' shape=(1, 3) dtype=float32,
numpy=array([[1., 1., 1.]], dtype=float32)>
>>> cast_input = tf.keras.backend.cast(input, dtype='float64')
>>> print(cast_input)
tf.Tensor([[1. 1. 1.]], shape=(1, 3), dtype=float64)
```

## Compat aliases

* `tf.compat.v1.keras.backend.cast`
* `tf.compat.v2.keras.backend.cast`

