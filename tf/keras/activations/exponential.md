<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.activations.exponential" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.activations.exponential

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/activations.py">View source</a>



Exponential activation function.

``` python
tf.keras.activations.exponential(x)
```



<!-- Placeholder for "Used in" -->


#### For example:



```
>>> a = tf.constant([-3.0,-1.0, 0.0,1.0,3.0], dtype = tf.float32)
>>> b = tf.keras.activations.exponential(a)
>>> b.numpy()
array([ 0.04978707,  0.36787945,  1.        ,  2.7182817 , 20.085537  ],
      dtype=float32)
```

#### Arguments:


* <b>`x`</b>: Input tensor.


#### Returns:

Tensor with exponential activation: `exp(x)`. Tensor will be of same
shape and dtype of input `x`.


## Compat aliases

* `tf.compat.v1.keras.activations.exponential`
* `tf.compat.v2.keras.activations.exponential`

