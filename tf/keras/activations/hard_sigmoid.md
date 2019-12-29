<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.activations.hard_sigmoid" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.activations.hard_sigmoid

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/activations.py">View source</a>



Hard sigmoid activation function.

``` python
tf.keras.activations.hard_sigmoid(x)
```



<!-- Placeholder for "Used in" -->

Faster to compute than sigmoid activation.

#### For example:



```
>>> a = tf.constant([-3.0,-1.0, 0.0,1.0,3.0], dtype = tf.float32)
>>> b = tf.keras.activations.hard_sigmoid(a)
>>> b.numpy()
array([0. , 0.3, 0.5, 0.7, 1. ], dtype=float32)
```

#### Arguments:


* <b>`x`</b>: Input tensor.


#### Returns:

The hard sigmoid activation:

  - `0` if `x < -2.5`
  - `1` if `x > 2.5`
  - `0.2 * x + 0.5` if `-2.5 <= x <= 2.5`.


## Compat aliases

* `tf.compat.v1.keras.activations.hard_sigmoid`
* `tf.compat.v2.keras.activations.hard_sigmoid`

