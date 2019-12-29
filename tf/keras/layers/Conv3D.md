<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.Conv3D" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
</div>

# tf.keras.layers.Conv3D

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/convolutional.py">View source</a>



## Class `Conv3D`

3D convolution layer (e.g. spatial convolution over volumes).



**Aliases**: `tf.keras.layers.Convolution3D`

<!-- Placeholder for "Used in" -->

This layer creates a convolution kernel that is convolved
with the layer input to produce a tensor of
outputs. If `use_bias` is True,
a bias vector is created and added to the outputs. Finally, if
`activation` is not `None`, it is applied to the outputs as well.

When using this layer as the first layer in a model,
provide the keyword argument `input_shape`
(tuple of integers, does not include the sample axis),
e.g. `input_shape=(128, 128, 128, 1)` for 128x128x128 volumes
with a single channel,
in `data_format="channels_last"`.

#### Examples:



```
>>> # The inputs are 28x28x28 volumes with a single channel, and the
>>> # batch size is 4
>>> input_shape =(4, 28, 28, 28, 1)
>>> x = tf.random.normal(input_shape)
>>> y = tf.keras.layers.Conv3D(
... 2, 3, activation='relu', input_shape=input_shape)(x)
>>> print(y.shape)
(4, 26, 26, 26, 2)
```

#### Arguments:


* <b>`filters`</b>: Integer, the dimensionality of the output space
  (i.e. the number of output filters in the convolution).
* <b>`kernel_size`</b>: An integer or tuple/list of 3 integers, specifying the
  depth, height and width of the 3D convolution window.
  Can be a single integer to specify the same value for
  all spatial dimensions.
* <b>`strides`</b>: An integer or tuple/list of 3 integers,
  specifying the strides of the convolution along each spatial
    dimension.
  Can be a single integer to specify the same value for
  all spatial dimensions.
  Specifying any stride value != 1 is incompatible with specifying
  any `dilation_rate` value != 1.
* <b>`padding`</b>: one of `"valid"` or `"same"` (case-insensitive).
* <b>`data_format`</b>: A string,
  one of `channels_last` (default) or `channels_first`.
  The ordering of the dimensions in the inputs.
  `channels_last` corresponds to inputs with shape
  `(batch_size, spatial_dim1, spatial_dim2, spatial_dim3, channels)`
  while `channels_first` corresponds to inputs with shape
  `(batch_size, channels, spatial_dim1, spatial_dim2, spatial_dim3)`.
  It defaults to the `image_data_format` value found in your
  Keras config file at `~/.keras/keras.json`.
  If you never set it, then it will be "channels_last".
* <b>`dilation_rate`</b>: an integer or tuple/list of 3 integers, specifying
  the dilation rate to use for dilated convolution.
  Can be a single integer to specify the same value for
  all spatial dimensions.
  Currently, specifying any `dilation_rate` value != 1 is
  incompatible with specifying any stride value != 1.
* <b>`activation`</b>: Activation function to use.
  If you don't specify anything, no activation is applied (
  see <a href="../../../tf/keras/activations.md"><code>keras.activations</code></a>).
* <b>`use_bias`</b>: Boolean, whether the layer uses a bias vector.
* <b>`kernel_initializer`</b>: Initializer for the `kernel` weights matrix (
  see <a href="../../../tf/keras/initializers.md"><code>keras.initializers</code></a>).
* <b>`bias_initializer`</b>: Initializer for the bias vector (
  see <a href="../../../tf/keras/initializers.md"><code>keras.initializers</code></a>).
* <b>`kernel_regularizer`</b>: Regularizer function applied to
  the `kernel` weights matrix (
  see <a href="../../../tf/keras/regularizers.md"><code>keras.regularizers</code></a>).
* <b>`bias_regularizer`</b>: Regularizer function applied to the bias vector (
  see <a href="../../../tf/keras/regularizers.md"><code>keras.regularizers</code></a>).
* <b>`activity_regularizer`</b>: Regularizer function applied to
  the output of the layer (its "activation") (
  see <a href="../../../tf/keras/regularizers.md"><code>keras.regularizers</code></a>).
* <b>`kernel_constraint`</b>: Constraint function applied to the kernel matrix (
  see <a href="../../../tf/keras/constraints.md"><code>keras.constraints</code></a>).
* <b>`bias_constraint`</b>: Constraint function applied to the bias vector (
  see <a href="../../../tf/keras/constraints.md"><code>keras.constraints</code></a>).


#### Input shape:

5D tensor with shape:
`(batch_size, channels, conv_dim1, conv_dim2, conv_dim3)` if
  data_format='channels_first'
or 5D tensor with shape:
`(batch_size, conv_dim1, conv_dim2, conv_dim3, channels)` if
  data_format='channels_last'.



#### Output shape:

5D tensor with shape:
`(batch_size, filters, new_conv_dim1, new_conv_dim2, new_conv_dim3)` if
  data_format='channels_first'
or 5D tensor with shape:
`(batch_size, new_conv_dim1, new_conv_dim2, new_conv_dim3, filters)` if
  data_format='channels_last'.
`new_conv_dim1`, `new_conv_dim2` and `new_conv_dim3` values might have
  changed due to padding.



#### Returns:

A tensor of rank 5 representing
`activation(conv3d(inputs, kernel) + bias)`.



#### Raises:


* <b>`ValueError`</b>: if `padding` is "causal".
* <b>`ValueError`</b>: when both `strides` > 1 and `dilation_rate` > 1.

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/convolutional.py">View source</a>

``` python
__init__(
    filters,
    kernel_size,
    strides=(1, 1, 1),
    padding='valid',
    data_format=None,
    dilation_rate=(1, 1, 1),
    activation=None,
    use_bias=True,
    kernel_initializer='glorot_uniform',
    bias_initializer='zeros',
    kernel_regularizer=None,
    bias_regularizer=None,
    activity_regularizer=None,
    kernel_constraint=None,
    bias_constraint=None,
    **kwargs
)
```








## Compat aliases

* `tf.compat.v1.keras.layers.Conv3D`
* `tf.compat.v1.keras.layers.Convolution3D`
* `tf.compat.v2.keras.layers.Conv3D`
* `tf.compat.v2.keras.layers.Convolution3D`

