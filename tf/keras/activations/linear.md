<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.activations.linear" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.activations.linear

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/activations.py">View source</a>



Linear activation function.

``` python
tf.keras.activations.linear(x)
```



<!-- Placeholder for "Used in" -->


#### For example:



```
>>> a = tf.constant([-3.0,-1.0, 0.0,1.0,3.0], dtype = tf.float32)
>>> b = tf.keras.activations.linear(a)
>>> b.numpy()
array([-3., -1.,  0.,  1.,  3.], dtype=float32)
```

#### Arguments:


* <b>`x`</b>: Input tensor.


#### Returns:

the input unmodified.


## Compat aliases

* `tf.compat.v1.keras.activations.linear`
* `tf.compat.v2.keras.activations.linear`

