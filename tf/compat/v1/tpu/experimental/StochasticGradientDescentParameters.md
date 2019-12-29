<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.tpu.experimental.StochasticGradientDescentParameters" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
</div>

# tf.compat.v1.tpu.experimental.StochasticGradientDescentParameters

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/tpu/tpu_embedding.py">View source</a>



## Class `StochasticGradientDescentParameters`

Optimization parameters for stochastic gradient descent for TPU embeddings.



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
        optimization_parameters=(
            tf.tpu.experimental.StochasticGradientDescentParameters(0.1))))
```

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/tpu/tpu_embedding.py">View source</a>

``` python
__init__(
    learning_rate,
    clip_weight_min=None,
    clip_weight_max=None
)
```

Optimization parameters for stochastic gradient descent.


#### Args:


* <b>`learning_rate`</b>: a floating point value. The learning rate.
* <b>`clip_weight_min`</b>: the minimum value to clip by; None means -infinity.
* <b>`clip_weight_max`</b>: the maximum value to clip by; None means +infinity.





