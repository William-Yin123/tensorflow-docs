<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.activations.relu" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.activations.relu

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/activations.py">View source</a>



Applies the rectified linear unit activation function.

``` python
tf.keras.activations.relu(
    x,
    alpha=0.0,
    max_value=None,
    threshold=0
)
```



<!-- Placeholder for "Used in" -->

With default values, this returns the standard ReLU activation:
`max(x, 0)`, the element-wise maximum of 0 and the input tensor.

Modifying default parameters allows you to use non-zero thresholds,
change the max value of the activation,
and to use a non-zero multiple of the input for values below the threshold.

#### For example:


>>> foo = tf.constant([-10, -5, 0.0, 5, 10], dtype = tf.float32)
>>> tf.keras.activations.relu(foo).numpy()
array([ 0.,  0.,  0.,  5., 10.], dtype=float32)
>>> tf.keras.activations.relu(foo, alpha=0.5).numpy()
array([-5. , -2.5,  0. ,  5. , 10. ], dtype=float32)
>>> tf.keras.activations.relu(foo, max_value=5).numpy()
array([0., 0., 0., 5., 5.], dtype=float32)
>>> tf.keras.activations.relu(foo, threshold=5).numpy()
array([-0., -0.,  0.,  0., 10.], dtype=float32)

#### Arguments:


* <b>`x`</b>: Input `tensor` or `variable`.
* <b>`alpha`</b>: A `float` that governs the slope for values lower than the
  threshold.
* <b>`max_value`</b>: A `float` that sets the saturation threshold (the largest value
  the function will return).
* <b>`threshold`</b>: A `float` giving the threshold value of the activation function
  below which values will be damped or set to zero.


#### Returns:

A `Tensor` representing the input tensor,
transformed by the relu activation function.
Tensor will be of the same shape and dtype of input `x`.


## Compat aliases

* `tf.compat.v1.keras.activations.relu`
* `tf.compat.v2.keras.activations.relu`

