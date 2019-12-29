<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.MaxPool2D" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
</div>

# tf.keras.layers.MaxPool2D

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/pooling.py">View source</a>



## Class `MaxPool2D`

Max pooling operation for 2D spatial data.



**Aliases**: `tf.keras.layers.MaxPooling2D`

<!-- Placeholder for "Used in" -->

Downsamples the input representation by taking the maximum value over the
window defined by `pool_size` for each dimension along the features axis.
The window is shifted by `strides` in each dimension.  The resulting output
when using "valid" padding option has a shape(number of rows or columns) of:
`output_shape = (input_shape - pool_size + 1) / strides)`

The resulting output shape when using the "same" padding option is:
`output_shape = input_shape / strides`

For example, for stride=(1,1) and padding="valid":

```
>>> x = tf.constant([[1., 2., 3.],
...                  [4., 5., 6.],
...                  [7., 8., 9.]])
>>> x = tf.reshape(x, [1, 3, 3, 1])
>>> max_pool_2d = tf.keras.layers.MaxPooling2D(pool_size=(2, 2),
...    strides=(1, 1), padding='valid')
>>> max_pool_2d(x)
<tf.Tensor: shape=(1, 2, 2, 1), dtype=float32, numpy=
  array([[[[5.],
           [6.]],
          [[8.],
           [9.]]]], dtype=float32)>
```

For example, for stride=(2,2) and padding="valid":

```
>>> x = tf.constant([[1., 2., 3., 4.],
...                  [5., 6., 7., 8.],
...                  [9., 10., 11., 12.]])
>>> x = tf.reshape(x, [1, 3, 4, 1])
>>> max_pool_2d = tf.keras.layers.MaxPooling2D(pool_size=(2, 2),
...    strides=(1, 1), padding='valid')
>>> max_pool_2d(x)
<tf.Tensor: shape=(1, 2, 3, 1), dtype=float32, numpy=
  array([[[[ 6.],
           [ 7.],
           [ 8.]],
          [[10.],
           [11.],
           [12.]]]], dtype=float32)>
```

For example, for stride=(1,1) and padding="same":

```
>>> x = tf.constant([[1., 2., 3.],
...                  [4., 5., 6.],
...                  [7., 8., 9.]])
>>> x = tf.reshape(x, [1, 3, 3, 1])
>>> max_pool_2d = tf.keras.layers.MaxPooling2D(pool_size=(2, 2),
...    strides=(1, 1), padding='same')
>>> max_pool_2d(x)
<tf.Tensor: shape=(1, 3, 3, 1), dtype=float32, numpy=
  array([[[[5.],
           [6.],
           [6.]],
          [[8.],
           [9.],
           [9.]],
          [[8.],
           [9.],
           [9.]]]], dtype=float32)>
```

#### Arguments:


* <b>`pool_size`</b>: integer or tuple of 2 integers,
  window size over which to take the maximum.
  `(2, 2)` will take the max value over a 2x2 pooling window.
  If only one integer is specified, the same window length
  will be used for both dimensions.
* <b>`strides`</b>: Integer, tuple of 2 integers, or None.
  Strides values.  Specifies how far the pooling window moves
  for each pooling step. If None, it will default to `pool_size`.
* <b>`padding`</b>: One of `"valid"` or `"same"` (case-insensitive).
  "valid" adds no zero padding.  "same" adds padding such that if the stride
  is 1, the output shape is the same as input shape.
* <b>`data_format`</b>: A string,
  one of `channels_last` (default) or `channels_first`.
  The ordering of the dimensions in the inputs.
  `channels_last` corresponds to inputs with shape
  `(batch, height, width, channels)` while `channels_first`
  corresponds to inputs with shape
  `(batch, channels, height, width)`.
  It defaults to the `image_data_format` value found in your
  Keras config file at `~/.keras/keras.json`.
  If you never set it, then it will be "channels_last".


#### Input shape:

- If `data_format='channels_last'`:
  4D tensor with shape `(batch_size, rows, cols, channels)`.
- If `data_format='channels_first'`:
  4D tensor with shape `(batch_size, channels, rows, cols)`.



#### Output shape:

- If `data_format='channels_last'`:
  4D tensor with shape `(batch_size, pooled_rows, pooled_cols, channels)`.
- If `data_format='channels_first'`:
  4D tensor with shape `(batch_size, channels, pooled_rows, pooled_cols)`.



#### Returns:

A tensor of rank 4 representing the maximum pooled values.  See above for
output shape.


<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/pooling.py">View source</a>

``` python
__init__(
    pool_size=(2, 2),
    strides=None,
    padding='valid',
    data_format=None,
    **kwargs
)
```








## Compat aliases

* `tf.compat.v1.keras.layers.MaxPool2D`
* `tf.compat.v1.keras.layers.MaxPooling2D`
* `tf.compat.v2.keras.layers.MaxPool2D`
* `tf.compat.v2.keras.layers.MaxPooling2D`

