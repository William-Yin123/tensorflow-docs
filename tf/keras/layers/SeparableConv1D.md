<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.SeparableConv1D" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
</div>

# tf.keras.layers.SeparableConv1D

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/convolutional.py">View source</a>



## Class `SeparableConv1D`

Depthwise separable 1D convolution.



**Aliases**: `tf.keras.layers.SeparableConvolution1D`

<!-- Placeholder for "Used in" -->

This layer performs a depthwise convolution that acts separately on
channels, followed by a pointwise convolution that mixes channels.
If `use_bias` is True and a bias initializer is provided,
it adds a bias vector to the output.
It then optionally applies an activation function to produce the final output.

#### Arguments:


* <b>`filters`</b>: Integer, the dimensionality of the output space (i.e. the number
  of filters in the convolution).
* <b>`kernel_size`</b>: A single integer specifying the spatial
  dimensions of the filters.
* <b>`strides`</b>: A single integer specifying the strides
  of the convolution.
  Specifying any `stride` value != 1 is incompatible with specifying
  any `dilation_rate` value != 1.
* <b>`padding`</b>: One of `"valid"`, `"same"`, or `"causal"` (case-insensitive).
* <b>`data_format`</b>: A string, one of `channels_last` (default) or `channels_first`.
  The ordering of the dimensions in the inputs.
  `channels_last` corresponds to inputs with shape
  `(batch_size, length, channels)` while `channels_first` corresponds to
  inputs with shape `(batch_size, channels, length)`.
* <b>`dilation_rate`</b>: A single integer, specifying
  the dilation rate to use for dilated convolution.
  Currently, specifying any `dilation_rate` value != 1 is
  incompatible with specifying any stride value != 1.
* <b>`depth_multiplier`</b>: The number of depthwise convolution output channels for
  each input channel. The total number of depthwise convolution output
  channels will be equal to `num_filters_in * depth_multiplier`.
* <b>`activation`</b>: Activation function to use.
  If you don't specify anything, no activation is applied (
  see <a href="../../../tf/keras/activations.md"><code>keras.activations</code></a>).
* <b>`use_bias`</b>: Boolean, whether the layer uses a bias.
* <b>`depthwise_initializer`</b>: An initializer for the depthwise convolution kernel (
  see <a href="../../../tf/keras/initializers.md"><code>keras.initializers</code></a>).
* <b>`pointwise_initializer`</b>: An initializer for the pointwise convolution kernel (
  see <a href="../../../tf/keras/initializers.md"><code>keras.initializers</code></a>).
* <b>`bias_initializer`</b>: An initializer for the bias vector. If None, the default
  initializer will be used (see <a href="../../../tf/keras/initializers.md"><code>keras.initializers</code></a>).
* <b>`depthwise_regularizer`</b>: Optional regularizer for the depthwise
  convolution kernel (see <a href="../../../tf/keras/regularizers.md"><code>keras.regularizers</code></a>).
* <b>`pointwise_regularizer`</b>: Optional regularizer for the pointwise
  convolution kernel (see <a href="../../../tf/keras/regularizers.md"><code>keras.regularizers</code></a>).
* <b>`bias_regularizer`</b>: Optional regularizer for the bias vector (
  see <a href="../../../tf/keras/regularizers.md"><code>keras.regularizers</code></a>).
* <b>`activity_regularizer`</b>: Optional regularizer function for the output (
  see <a href="../../../tf/keras/regularizers.md"><code>keras.regularizers</code></a>).
* <b>`depthwise_constraint`</b>: Optional projection function to be applied to the
  depthwise kernel after being updated by an `Optimizer` (e.g. used for
  norm constraints or value constraints for layer weights). The function
  must take as input the unprojected variable and must return the
  projected variable (which must have the same shape). Constraints are
  not safe to use when doing asynchronous distributed training (
  see <a href="../../../tf/keras/constraints.md"><code>keras.constraints</code></a>).
* <b>`pointwise_constraint`</b>: Optional projection function to be applied to the
  pointwise kernel after being updated by an `Optimizer` (
  see <a href="../../../tf/keras/constraints.md"><code>keras.constraints</code></a>).
* <b>`bias_constraint`</b>: Optional projection function to be applied to the
  bias after being updated by an `Optimizer` (
  see <a href="../../../tf/keras/constraints.md"><code>keras.constraints</code></a>).
* <b>`trainable`</b>: Boolean, if `True` the weights of this layer will be marked as
  trainable (and listed in `layer.trainable_weights`).
* <b>`name`</b>: A string, the name of the layer.


#### Input shape:

3D tensor with shape:
`(batch_size, channels, steps)` if data_format='channels_first'
or 5D tensor with shape:
`(batch_size, steps, channels)` if data_format='channels_last'.



#### Output shape:

3D tensor with shape:
`(batch_size, filters, new_steps)` if data_format='channels_first'
or 3D tensor with shape:
`(batch_size,  new_steps, filters)` if data_format='channels_last'.
`new_steps` value might have changed due to padding or strides.



#### Returns:

A tensor of rank 3 representing
`activation(separableconv1d(inputs, kernel) + bias)`.



#### Raises:


* <b>`ValueError`</b>: when both `strides` > 1 and `dilation_rate` > 1.

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/convolutional.py">View source</a>

``` python
__init__(
    filters,
    kernel_size,
    strides=1,
    padding='valid',
    data_format=None,
    dilation_rate=1,
    depth_multiplier=1,
    activation=None,
    use_bias=True,
    depthwise_initializer='glorot_uniform',
    pointwise_initializer='glorot_uniform',
    bias_initializer='zeros',
    depthwise_regularizer=None,
    pointwise_regularizer=None,
    bias_regularizer=None,
    activity_regularizer=None,
    depthwise_constraint=None,
    pointwise_constraint=None,
    bias_constraint=None,
    **kwargs
)
```








## Compat aliases

* `tf.compat.v1.keras.layers.SeparableConv1D`
* `tf.compat.v1.keras.layers.SeparableConvolution1D`
* `tf.compat.v2.keras.layers.SeparableConv1D`
* `tf.compat.v2.keras.layers.SeparableConvolution1D`

