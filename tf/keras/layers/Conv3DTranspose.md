<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.Conv3DTranspose" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
</div>

# tf.keras.layers.Conv3DTranspose

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/convolutional.py">View source</a>



## Class `Conv3DTranspose`

Transposed convolution layer (sometimes called Deconvolution).

Inherits From: [`Conv3D`](../../../tf/keras/layers/Conv3D.md)

**Aliases**: `tf.keras.layers.Convolution3DTranspose`

<!-- Placeholder for "Used in" -->

The need for transposed convolutions generally arises
from the desire to use a transformation going in the opposite direction
of a normal convolution, i.e., from something that has the shape of the
output of some convolution to something that has the shape of its input
while maintaining a connectivity pattern that is compatible with
said convolution.

When using this layer as the first layer in a model,
provide the keyword argument `input_shape`
(tuple of integers, does not include the sample axis),
e.g. `input_shape=(128, 128, 128, 3)` for a 128x128x128 volume with 3 channels
if `data_format="channels_last"`.

#### Arguments:


* <b>`filters`</b>: Integer, the dimensionality of the output space
    (i.e. the number of output filters in the convolution).
* <b>`kernel_size`</b>: An integer or tuple/list of 3 integers, specifying the
    depth, height and width of the 3D convolution window.
    Can be a single integer to specify the same value for
    all spatial dimensions.
* <b>`strides`</b>: An integer or tuple/list of 3 integers,
    specifying the strides of the convolution along the depth, height
      and width.
    Can be a single integer to specify the same value for
    all spatial dimensions.
    Specifying any stride value != 1 is incompatible with specifying
    any `dilation_rate` value != 1.
* <b>`padding`</b>: one of `"valid"` or `"same"` (case-insensitive).
* <b>`output_padding`</b>: An integer or tuple/list of 3 integers,
  specifying the amount of padding along the depth, height, and
  width.
  Can be a single integer to specify the same value for all
  spatial dimensions.
  The amount of output padding along a given dimension must be
  lower than the stride along that same dimension.
  If set to `None` (default), the output shape is inferred.
* <b>`data_format`</b>: A string,
  one of `channels_last` (default) or `channels_first`.
  The ordering of the dimensions in the inputs.
  `channels_last` corresponds to inputs with shape
  `(batch_size, depth, height, width, channels)` while `channels_first`
  corresponds to inputs with shape
  `(batch_size, channels, depth, height, width)`.
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
* <b>`kernel_initializer`</b>: Initializer for the `kernel` weights matrix.
* <b>`bias_initializer`</b>: Initializer for the bias vector.
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
`(batch_size, channels, depth, rows, cols)` if data_format='channels_first'
or 5D tensor with shape:
`(batch_size, depth, rows, cols, channels)` if data_format='channels_last'.



#### Output shape:

5D tensor with shape:
`(batch_size, filters, new_depth, new_rows, new_cols)` if
  data_format='channels_first'
or 5D tensor with shape:
`(batch_size, new_depth, new_rows, new_cols, filters)` if
  data_format='channels_last'.
`depth` and `rows` and `cols` values might have changed due to padding.
If `output_padding` is specified::
```
new_depth = ((depth - 1) * strides[0] + kernel_size[0] - 2 * padding[0] +
output_padding[0])
new_rows = ((rows - 1) * strides[1] + kernel_size[1] - 2 * padding[1] +
output_padding[1])
new_cols = ((cols - 1) * strides[2] + kernel_size[2] - 2 * padding[2] +
output_padding[2])
```



#### Returns:

A tensor of rank 5 representing
`activation(conv3dtranspose(inputs, kernel) + bias)`.



#### Raises:


* <b>`ValueError`</b>: if `padding` is "causal".
* <b>`ValueError`</b>: when both `strides` > 1 and `dilation_rate` > 1.


#### References:

- [A guide to convolution arithmetic for deep
  learning](https://arxiv.org/abs/1603.07285v1)
- [Deconvolutional
  Networks](https://www.matthewzeiler.com/mattzeiler/deconvolutionalnetworks.pdf)


<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/convolutional.py">View source</a>

``` python
__init__(
    filters,
    kernel_size,
    strides=(1, 1, 1),
    padding='valid',
    output_padding=None,
    data_format=None,
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

* `tf.compat.v1.keras.layers.Conv3DTranspose`
* `tf.compat.v1.keras.layers.Convolution3DTranspose`
* `tf.compat.v2.keras.layers.Conv3DTranspose`
* `tf.compat.v2.keras.layers.Convolution3DTranspose`

