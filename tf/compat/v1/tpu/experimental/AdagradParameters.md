<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.tpu.experimental.AdagradParameters" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
</div>

# tf.compat.v1.tpu.experimental.AdagradParameters

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/tpu/tpu_embedding.py">View source</a>



## Class `AdagradParameters`

Optimization parameters for Adagrad with TPU embeddings.



<!-- Placeholder for "Used in" -->

Pass this to `tf.estimator.tpu.experimental.EmbeddingConfigSpec` via the
`optimization_parameters` argument to set the optimizer and its parameters.
See the documentation for `tf.estimator.tpu.experimental.EmbeddingConfigSpec`
for more details.

```
estimator = tf.estimator.tpu.TPUEstimator(
    ...
    embedding_spec=tf.estimator.tpu.experimental.EmbeddingConfigSpec(
        ...
        optimization_parameters=tf.tpu.experimental.AdagradParameters(0.1),
        ...))
```

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/tpu/tpu_embedding.py">View source</a>

``` python
__init__(
    learning_rate,
    initial_accumulator=0.1,
    use_gradient_accumulation=True,
    clip_weight_min=None,
    clip_weight_max=None
)
```

Optimization parameters for Adagrad.


#### Args:


* <b>`learning_rate`</b>: used for updating embedding table.
* <b>`initial_accumulator`</b>: initial accumulator for Adagrad.
* <b>`use_gradient_accumulation`</b>: setting this to `False` makes embedding
  gradients calculation less accurate but faster. Please see
  `optimization_parameters.proto` for details.
  for details.
* <b>`clip_weight_min`</b>: the minimum value to clip by; None means -infinity.
* <b>`clip_weight_max`</b>: the maximum value to clip by; None means +infinity.





