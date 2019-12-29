<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.Cropping1D" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
</div>

# tf.keras.layers.Cropping1D

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/convolutional.py">View source</a>



## Class `Cropping1D`

Cropping layer for 1D input (e.g. temporal sequence).

Inherits From: [`Layer`](../../../tf/keras/layers/Layer.md)

<!-- Placeholder for "Used in" -->

It crops along the time dimension (axis 1).

#### Examples:



```
>>> input_shape = (2, 3, 2)
>>> x = np.arange(np.prod(input_shape)).reshape(input_shape)
>>> print(x)
[[[ 0  1]
  [ 2  3]
  [ 4  5]]
 [[ 6  7]
  [ 8  9]
  [10 11]]]
>>> y = tf.keras.layers.Cropping1D(cropping=1)(x)
>>> print(y)
tf.Tensor(
  [[[2 3]]
   [[8 9]]], shape=(2, 1, 2), dtype=int64)
```

#### Arguments:


* <b>`cropping`</b>: Int or tuple of int (length 2)
  How many units should be trimmed off at the beginning and end of
  the cropping dimension (axis 1).
  If a single int is provided, the same value will be used for both.


#### Input shape:

3D tensor with shape `(batch_size, axis_to_crop, features)`



#### Output shape:

3D tensor with shape `(batch_size, cropped_axis, features)`


<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/convolutional.py">View source</a>

``` python
__init__(
    cropping=(1, 1),
    **kwargs
)
```








## Compat aliases

* `tf.compat.v1.keras.layers.Cropping1D`
* `tf.compat.v2.keras.layers.Cropping1D`

