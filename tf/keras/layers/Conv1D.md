<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.Conv1D" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
</div>

# tf.keras.layers.Conv1D

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/convolutional.py">View source</a>



## Class `Conv1D`

1D convolution layer (e.g. temporal convolution).



**Aliases**: `tf.keras.layers.Convolution1D`

<!-- Placeholder for "Used in" -->

This layer creates a convolution kernel that is convolved
with the layer input over a single spatial (or temporal) dimension
to produce a tensor of outputs.
If `use_bias` is True, a bias vector is created and added to the outputs.
Finally, if `activation` is not `None`,
it is applied to the outputs as well.

When using this layer as the first layer in a model,
provide an `input_shape` argument
(tuple of integers or `None`, e.g.
`(10, 128)` for sequences of 10 vectors of 128-dimensional vectors,
or `(None, 128)` for variable-length sequences of 128-dimensional vectors.

#### Examples:



```
>>> # The inputs are 128-length vectors with 10 timesteps, and the batch size
>>> # is 4.
>>> input_shape = (4, 10, 128)
>>> x = tf.random.normal(input_shape)
>>> y = tf.keras.layers.Conv1D(
... 32, 3, activation='relu',input_shape=input_shape)(x)
>>> print(y.shape)
(4, 8, 32)
```

#### Arguments:


* <b>`filters`</b>: Integer, the dimensionality of the output space
  (i.e. the number of output filters in the convolution).
* <b>`kernel_size`</b>: An integer or tuple/list of a single integer,
  specifying the length of the 1D convolution window.
* <b>`strides`</b>: An integer or tuple/list of a single integer,
  specifying the stride length of the convolution.
  Specifying any stride value != 1 is incompatible with specifying
  any `dilation_rate` value != 1.
* <b>`padding`</b>: One of `"valid"`, `"causal"` or `"same"` (case-insensitive).
  `"causal"` results in causal (dilated) convolutions, e.g. `output[t]`
  does not depend on `input[t+1:]`. Useful when modeling temporal data
  where the model should not violate the temporal order.
  See [WaveNet: A Generative Model for Raw Audio, section
    2.1](https://arxiv.org/abs/1609.03499).
* <b>`data_format`</b>: A string,
  one of `channels_last` (default) or `channels_first`.
* <b>`dilation_rate`</b>: an integer or tuple/list of a single integer, specifying
  the dilation rate to use for dilated convolution.
  Currently, specifying any `dilation_rate` value != 1 is
  incompatible with specifying any `strides` value != 1.
* <b>`activation`</b>: Activation function to use.
  If you don't specify anything, no activation is applied (
  see <a href="../../../tf/keras/activations.md"><code>keras.activations</code></a>).
* <b>`use_bias`</b>: Boolean, whether the layer uses a bias vector.
* <b>`kernel_initializer`</b>: Initializer for the `kernel` weights matrix (
  see <a href="../../../tf/keras/initializers.md"><code>keras.initializers</code></a>).
* <b>`bias_initializer`</b>: Initializer for the bias vector (
  see <a href="../../../tf/keras/initializers.md"><code>keras.initializers</code></a>).
* <b>`kernel_regularizer`</b>: Regularizer function applied to
  the `kernel` weights matrix (see <a href="../../../tf/keras/regularizers.md"><code>keras.regularizers</code></a>).
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

3D tensor with shape: `(batch_size, steps, input_dim)`



#### Output shape:

3D tensor with shape: `(batch_size, new_steps, filters)`
  `steps` value might have changed due to padding or strides.



#### Returns:

A tensor of rank 3 representing
`activation(conv1d(inputs, kernel) + bias)`.



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
    data_format='channels_last',
    dilation_rate=1,
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

* `tf.compat.v1.keras.layers.Conv1D`
* `tf.compat.v1.keras.layers.Convolution1D`
* `tf.compat.v2.keras.layers.Conv1D`
* `tf.compat.v2.keras.layers.Convolution1D`

