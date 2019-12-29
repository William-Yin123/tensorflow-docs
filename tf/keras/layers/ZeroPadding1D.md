<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.ZeroPadding1D" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
</div>

# tf.keras.layers.ZeroPadding1D

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/convolutional.py">View source</a>



## Class `ZeroPadding1D`

Zero-padding layer for 1D input (e.g. temporal sequence).

Inherits From: [`Layer`](../../../tf/keras/layers/Layer.md)

<!-- Placeholder for "Used in" -->


#### Examples:



```
>>> input_shape = (2, 2, 3)
>>> x = np.arange(np.prod(input_shape)).reshape(input_shape)
>>> print(x)
[[[ 0  1  2]
  [ 3  4  5]]
 [[ 6  7  8]
  [ 9 10 11]]]
>>> y = tf.keras.layers.ZeroPadding1D(padding=2)(x)
>>> print(y)
tf.Tensor(
  [[[ 0  0  0]
    [ 0  0  0]
    [ 0  1  2]
    [ 3  4  5]
    [ 0  0  0]
    [ 0  0  0]]
   [[ 0  0  0]
    [ 0  0  0]
    [ 6  7  8]
    [ 9 10 11]
    [ 0  0  0]
    [ 0  0  0]]], shape=(2, 6, 3), dtype=int64)
```

#### Arguments:


* <b>`padding`</b>: Int, or tuple of int (length 2), or dictionary.
    - If int:
    How many zeros to add at the beginning and end of
    the padding dimension (axis 1).
    - If tuple of int (length 2):
    How many zeros to add at the beginning and at the end of
    the padding dimension (`(left_pad, right_pad)`).


#### Input shape:

3D tensor with shape `(batch_size, axis_to_pad, features)`



#### Output shape:

3D tensor with shape `(batch_size, padded_axis, features)`


<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/convolutional.py">View source</a>

``` python
__init__(
    padding=1,
    **kwargs
)
```








## Compat aliases

* `tf.compat.v1.keras.layers.ZeroPadding1D`
* `tf.compat.v2.keras.layers.ZeroPadding1D`

