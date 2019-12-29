<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.UpSampling2D" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
</div>

# tf.keras.layers.UpSampling2D

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/convolutional.py">View source</a>



## Class `UpSampling2D`

Upsampling layer for 2D inputs.

Inherits From: [`Layer`](../../../tf/keras/layers/Layer.md)

<!-- Placeholder for "Used in" -->

Repeats the rows and columns of the data
by `size[0]` and `size[1]` respectively.

#### Examples:



```
>>> input_shape = (2, 2, 1, 3)
>>> x = np.arange(np.prod(input_shape)).reshape(input_shape)
>>> print(x)
[[[[ 0  1  2]]
  [[ 3  4  5]]]
 [[[ 6  7  8]]
  [[ 9 10 11]]]]
>>> y = tf.keras.layers.UpSampling2D(size=(1, 2))(x)
>>> print(y)
tf.Tensor(
  [[[[ 0  1  2]
     [ 0  1  2]]
    [[ 3  4  5]
     [ 3  4  5]]]
   [[[ 6  7  8]
     [ 6  7  8]]
    [[ 9 10 11]
     [ 9 10 11]]]], shape=(2, 2, 2, 3), dtype=int64)
```

#### Arguments:


* <b>`size`</b>: Int, or tuple of 2 integers.
  The upsampling factors for rows and columns.
* <b>`data_format`</b>: A string,
  one of `channels_last` (default) or `channels_first`.
  The ordering of the dimensions in the inputs.
  `channels_last` corresponds to inputs with shape
  `(batch_size, height, width, channels)` while `channels_first`
  corresponds to inputs with shape
  `(batch_size, channels, height, width)`.
  It defaults to the `image_data_format` value found in your
  Keras config file at `~/.keras/keras.json`.
  If you never set it, then it will be "channels_last".
* <b>`interpolation`</b>: A string, one of `nearest` or `bilinear`.


#### Input shape:

4D tensor with shape:
- If `data_format` is `"channels_last"`:
    `(batch_size, rows, cols, channels)`
- If `data_format` is `"channels_first"`:
    `(batch_size, channels, rows, cols)`



#### Output shape:

4D tensor with shape:
- If `data_format` is `"channels_last"`:
    `(batch_size, upsampled_rows, upsampled_cols, channels)`
- If `data_format` is `"channels_first"`:
    `(batch_size, channels, upsampled_rows, upsampled_cols)`


<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/convolutional.py">View source</a>

``` python
__init__(
    size=(2, 2),
    data_format=None,
    interpolation='nearest',
    **kwargs
)
```








## Compat aliases

* `tf.compat.v1.keras.layers.UpSampling2D`
* `tf.compat.v2.keras.layers.UpSampling2D`

