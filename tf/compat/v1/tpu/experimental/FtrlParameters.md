<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.tpu.experimental.FtrlParameters" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
</div>

# tf.compat.v1.tpu.experimental.FtrlParameters

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/tpu/tpu_embedding.py">View source</a>



## Class `FtrlParameters`

Optimization parameters for Ftrl with TPU embeddings.



<!-- Placeholder for "Used in" -->

Pass this to `tf.estimator.tpu.experimental.EmbeddingConfigSpec` via the
`optimization_parameters` argument to set the optimizer and its parameters.
See the documentation for `tf.estimator.tpu.experimental.EmbeddingConfigSpec`
for more details.

```
estimator = tf.estimator.tpu.TPUEstimator(
    ...
    embedding_config_spec=tf.estimator.tpu.experimental.EmbeddingConfigSpec(
        ...
        optimization_parameters=tf.tpu.experimental.FtrlParameters(0.1),
        ...))
```

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/tpu/tpu_embedding.py">View source</a>

``` python
__init__(
    learning_rate,
    learning_rate_power=-0.5,
    initial_accumulator_value=0.1,
    l1_regularization_strength=0.0,
    l2_regularization_strength=0.0,
    use_gradient_accumulation=True,
    clip_weight_min=None,
    clip_weight_max=None
)
```

Optimization parameters for Ftrl.


#### Args:


* <b>`learning_rate`</b>: a floating point value. The learning rate.
* <b>`learning_rate_power`</b>: A float value, must be less or equal to zero.
  Controls how the learning rate decreases during training. Use zero for
  a fixed learning rate. See section 3.1 in the
  [paper](https://www.eecs.tufts.edu/~dsculley/papers/ad-click-prediction.pdf).
* <b>`initial_accumulator_value`</b>: The starting value for accumulators.
  Only zero or positive values are allowed.
* <b>`l1_regularization_strength`</b>: A float value, must be greater than or
  equal to zero.
* <b>`l2_regularization_strength`</b>: A float value, must be greater than or
  equal to zero.
* <b>`use_gradient_accumulation`</b>: setting this to `False` makes embedding
  gradients calculation less accurate but faster. Please see
  `optimization_parameters.proto` for details.
  for details.
* <b>`clip_weight_min`</b>: the minimum value to clip by; None means -infinity.
* <b>`clip_weight_max`</b>: the maximum value to clip by; None means +infinity.





