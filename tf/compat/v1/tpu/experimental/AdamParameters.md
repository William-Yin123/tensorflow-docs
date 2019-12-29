<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.tpu.experimental.AdamParameters" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
</div>

# tf.compat.v1.tpu.experimental.AdamParameters

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/tpu/tpu_embedding.py">View source</a>



## Class `AdamParameters`

Optimization parameters for Adam with TPU embeddings.



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
        optimization_parameters=tf.tpu.experimental.AdamParameters(0.1),
        ...))
```

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/tpu/tpu_embedding.py">View source</a>

``` python
__init__(
    learning_rate,
    beta1=0.9,
    beta2=0.999,
    epsilon=1e-08,
    lazy_adam=True,
    sum_inside_sqrt=True,
    use_gradient_accumulation=True,
    clip_weight_min=None,
    clip_weight_max=None
)
```

Optimization parameters for Adam.


#### Args:


* <b>`learning_rate`</b>: a floating point value. The learning rate.
* <b>`beta1`</b>: A float value.
  The exponential decay rate for the 1st moment estimates.
* <b>`beta2`</b>: A float value.
  The exponential decay rate for the 2nd moment estimates.
* <b>`epsilon`</b>: A small constant for numerical stability.
* <b>`lazy_adam`</b>: Use lazy Adam instead of Adam. Lazy Adam trains faster.
  Please see `optimization_parameters.proto` for details.
* <b>`sum_inside_sqrt`</b>: This improves training speed. Please see
  `optimization_parameters.proto` for details.
* <b>`use_gradient_accumulation`</b>: setting this to `False` makes embedding
  gradients calculation less accurate but faster. Please see
  `optimization_parameters.proto` for details.
  for details.
* <b>`clip_weight_min`</b>: the minimum value to clip by; None means -infinity.
* <b>`clip_weight_max`</b>: the maximum value to clip by; None means +infinity.





