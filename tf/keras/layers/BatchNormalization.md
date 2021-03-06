<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.BatchNormalization" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
</div>

# tf.keras.layers.BatchNormalization

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/normalization_v2.py">View source</a>



## Class `BatchNormalization`

Normalize and scale inputs or activations. (Ioffe and Szegedy, 2014).



<!-- Placeholder for "Used in" -->

Normalize the activations of the previous layer at each batch,
i.e. applies a transformation that maintains the mean activation
close to 0 and the activation standard deviation close to 1.

Batch normalization differs from other layers in several key aspects:

1) Adding BatchNormalization with `training=True` to a model causes the
result of one example to depend on the contents of all other examples in a
minibatch. Be careful when padding batches or masking examples, as these can
change the minibatch statistics and affect other examples.

2) Updates to the weights (moving statistics) are based on the forward pass
of a model rather than the result of gradient computations.

3) When performing inference using a model containing batch normalization, it
is generally (though not always) desirable to use accumulated statistics
rather than mini-batch statistics. This is acomplished by passing
`training=False` when calling the model, or using `model.predict`.

#### Arguments:


* <b>`axis`</b>: Integer, the axis that should be normalized
  (typically the features axis).
  For instance, after a `Conv2D` layer with
  `data_format="channels_first"`,
  set `axis=1` in `BatchNormalization`.
* <b>`momentum`</b>: Momentum for the moving average.
* <b>`epsilon`</b>: Small float added to variance to avoid dividing by zero.
* <b>`center`</b>: If True, add offset of `beta` to normalized tensor.
  If False, `beta` is ignored.
* <b>`scale`</b>: If True, multiply by `gamma`.
  If False, `gamma` is not used.
  When the next layer is linear (also e.g. <a href="../../../tf/nn/relu.md"><code>nn.relu</code></a>),
  this can be disabled since the scaling
  will be done by the next layer.
* <b>`beta_initializer`</b>: Initializer for the beta weight.
* <b>`gamma_initializer`</b>: Initializer for the gamma weight.
* <b>`moving_mean_initializer`</b>: Initializer for the moving mean.
* <b>`moving_variance_initializer`</b>: Initializer for the moving variance.
* <b>`beta_regularizer`</b>: Optional regularizer for the beta weight.
* <b>`gamma_regularizer`</b>: Optional regularizer for the gamma weight.
* <b>`beta_constraint`</b>: Optional constraint for the beta weight.
* <b>`gamma_constraint`</b>: Optional constraint for the gamma weight.
* <b>`renorm`</b>: Whether to use Batch Renormalization
  (https://arxiv.org/abs/1702.03275). This adds extra variables during
  training. The inference is the same for either value of this parameter.
* <b>`renorm_clipping`</b>: A dictionary that may map keys 'rmax', 'rmin', 'dmax' to
  scalar `Tensors` used to clip the renorm correction. The correction
  `(r, d)` is used as `corrected_value = normalized_value * r + d`, with
  `r` clipped to [rmin, rmax], and `d` to [-dmax, dmax]. Missing rmax, rmin,
  dmax are set to inf, 0, inf, respectively.
* <b>`renorm_momentum`</b>: Momentum used to update the moving means and standard
  deviations with renorm. Unlike `momentum`, this affects training
  and should be neither too small (which would add noise) nor too large
  (which would give stale estimates). Note that `momentum` is still applied
  to get the means and variances for inference.
* <b>`fused`</b>: if `True`, use a faster, fused implementation, or raise a ValueError
  if the fused implementation cannot be used. If `None`, use the faster
  implementation if possible. If False, do not used the fused
  implementation.
* <b>`trainable`</b>: Boolean, if `True` the variables will be marked as trainable.
* <b>`virtual_batch_size`</b>: An `int`. By default, `virtual_batch_size` is `None`,
  which means batch normalization is performed across the whole batch. When
  `virtual_batch_size` is not `None`, instead perform "Ghost Batch
  Normalization", which creates virtual sub-batches which are each
  normalized separately (with shared gamma, beta, and moving statistics).
  Must divide the actual batch size during execution.
* <b>`adjustment`</b>: A function taking the `Tensor` containing the (dynamic) shape of
  the input tensor and returning a pair (scale, bias) to apply to the
  normalized values (before gamma and beta), only during training. For
  example, if axis==-1,
    `adjustment = lambda shape: (
      tf.random.uniform(shape[-1:], 0.93, 1.07),
      tf.random.uniform(shape[-1:], -0.1, 0.1))`
  will scale the normalized value by up to 7% up or down, then shift the
  result by up to 0.1 (with independent scaling and bias for each feature
  but shared across all examples), and finally apply gamma and/or beta. If
  `None`, no adjustment is applied. Cannot be specified if
  virtual_batch_size is specified.


#### Call arguments:


* <b>`inputs`</b>: Input tensor (of any rank).
* <b>`training`</b>: Python boolean indicating whether the layer should behave in
  training mode or in inference mode.
  - `training=True`: The layer will normalize its inputs using the
    mean and variance of the current batch of inputs.
  - `training=False`: The layer will normalize its inputs using the
    mean and variance of its moving statistics, learned during training.


#### Input shape:

Arbitrary. Use the keyword argument `input_shape`
(tuple of integers, does not include the samples axis)
when using this layer as the first layer in a model.



#### Output shape:

Same shape as input.



**About setting `layer.trainable = False` on a `BatchNormalization layer:**

The meaning of setting `layer.trainable = False` is to freeze the layer,
i.e. its internal state will not change during training:
its trainable weights will not be updated
during `fit()` or `train_on_batch()`, and its state updates will not be run.

Usually, this does not necessarily mean that the layer is run in inference
mode (which is normally controlled by the `training` argument that can
be passed when calling a layer). "Frozen state" and "inference mode"
are two separate concepts.

However, in the case of the `BatchNormalization` layer, **setting
`trainable = False` on the layer means that the layer will be
subsequently run in inference mode** (meaning that it will use
the moving mean and the moving variance to normalize the current batch,
rather than using the mean and variance of the current batch).

This behavior has been introduced in TensorFlow 2.0, in order
to enable `layer.trainable = False` to produce the most commonly
expected behavior in the convnet fine-tuning use case.

#### Note that:

- This behavior only occurs as of TensorFlow 2.0. In 1.*,
  setting `layer.trainable = False` would freeze the layer but would
  not switch it to inference mode.
- Setting `trainable` on an model containing other layers will
  recursively set the `trainable` value of all inner layers.
- If the value of the `trainable`
  attribute is changed after calling `compile()` on a model,
  the new value doesn't take effect for this model
  until `compile()` is called again.



Normalization equations:
  Consider the intermediate activations \(x\) of a mini-batch of size
  \\(m\\):

  We can compute the mean and variance of the batch

  \\({\mu_B} = \frac{1}{m} \sum_{i=1}^{m} {x_i}\\)

  \\({\sigma_B^2} = \frac{1}{m} \sum_{i=1}^{m} ({x_i} - {\mu_B})^2\\)

  and then compute a normalized \\(x\\), including a small factor
  \\({\epsilon}\\) for numerical stability.

  \\(\hat{x_i} = \frac{x_i - \mu_B}{\sqrt{\sigma_B^2 + \epsilon}}\\)

  And finally \\(\hat{x}\) is linearly transformed by \({\gamma}\\)
  and \\({\beta}\\), which are learned parameters:

  \\({y_i} = {\gamma * \hat{x_i} + \beta}\\)

#### References:


- [Batch Normalization: Accelerating Deep Network Training by Reducing
  Internal Covariate Shift](https://arxiv.org/abs/1502.03167)

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/normalization.py">View source</a>

``` python
__init__(
    axis=-1,
    momentum=0.99,
    epsilon=0.001,
    center=True,
    scale=True,
    beta_initializer='zeros',
    gamma_initializer='ones',
    moving_mean_initializer='zeros',
    moving_variance_initializer='ones',
    beta_regularizer=None,
    gamma_regularizer=None,
    beta_constraint=None,
    gamma_constraint=None,
    renorm=False,
    renorm_clipping=None,
    renorm_momentum=0.99,
    fused=None,
    trainable=True,
    virtual_batch_size=None,
    adjustment=None,
    name=None,
    **kwargs
)
```








## Compat aliases

* `tf.compat.v2.keras.layers.BatchNormalization`

