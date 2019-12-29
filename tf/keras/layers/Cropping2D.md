<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.Cropping2D" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
</div>

# tf.keras.layers.Cropping2D

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/convolutional.py">View source</a>



## Class `Cropping2D`

Cropping layer for 2D input (e.g. picture).

Inherits From: [`Layer`](../../../tf/keras/layers/Layer.md)

<!-- Placeholder for "Used in" -->

It crops along spatial dimensions, i.e. height and width.

#### Examples:



```
>>> input_shape = (2, 28, 28, 3)
>>> x = np.arange(np.prod(input_shape)).reshape(input_shape)
>>> y = tf.keras.layers.Cropping2D(cropping=((2, 2), (4, 4)))(x)
>>> print(y.shape)
(2, 24, 20, 3)
```

#### Arguments:


* <b>`cropping`</b>: Int, or tuple of 2 ints, or tuple of 2 tuples of 2 ints.
  - If int: the same symmetric cropping
    is applied to height and width.
  - If tuple of 2 ints:
    interpreted as two different
    symmetric cropping values for height and width:
    `(symmetric_height_crop, symmetric_width_crop)`.
  - If tuple of 2 tuples of 2 ints:
    interpreted as
    `((top_crop, bottom_crop), (left_crop, right_crop))`
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


#### Input shape:

4D tensor with shape:
- If `data_format` is `"channels_last"`:
  `(batch_size, rows, cols, channels)`
- If `data_format` is `"channels_first"`:
  `(batch_size, channels, rows, cols)`



#### Output shape:

4D tensor with shape:
- If `data_format` is `"channels_last"`:
  `(batch_size, cropped_rows, cropped_cols, channels)`
- If `data_format` is `"channels_first"`:
  `(batch_size, channels, cropped_rows, cropped_cols)`


<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/convolutional.py">View source</a>

``` python
__init__(
    cropping=((0, 0), (0, 0)),
    data_format=None,
    **kwargs
)
```








## Compat aliases

* `tf.compat.v1.keras.layers.Cropping2D`
* `tf.compat.v2.keras.layers.Cropping2D`

