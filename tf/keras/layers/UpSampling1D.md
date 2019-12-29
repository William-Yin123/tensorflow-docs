<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.UpSampling1D" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
</div>

# tf.keras.layers.UpSampling1D

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/convolutional.py">View source</a>



## Class `UpSampling1D`

Upsampling layer for 1D inputs.

Inherits From: [`Layer`](../../../tf/keras/layers/Layer.md)

<!-- Placeholder for "Used in" -->

Repeats each temporal step `size` times along the time axis.

#### Examples:



```
>>> input_shape = (2, 2, 3)
>>> x = np.arange(np.prod(input_shape)).reshape(input_shape)
>>> print(x)
[[[ 0  1  2]
  [ 3  4  5]]
 [[ 6  7  8]
  [ 9 10 11]]]
>>> y = tf.keras.layers.UpSampling1D(size=2)(x)
>>> print(y)
tf.Tensor(
  [[[ 0  1  2]
    [ 0  1  2]
    [ 3  4  5]
    [ 3  4  5]]
   [[ 6  7  8]
    [ 6  7  8]
    [ 9 10 11]
    [ 9 10 11]]], shape=(2, 4, 3), dtype=int64)
```

#### Arguments:


* <b>`size`</b>: Integer. Upsampling factor.


#### Input shape:

3D tensor with shape: `(batch_size, steps, features)`.



#### Output shape:

3D tensor with shape: `(batch_size, upsampled_steps, features)`.


<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/convolutional.py">View source</a>

``` python
__init__(
    size=2,
    **kwargs
)
```








## Compat aliases

* `tf.compat.v1.keras.layers.UpSampling1D`
* `tf.compat.v2.keras.layers.UpSampling1D`

