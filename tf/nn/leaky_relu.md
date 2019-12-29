<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.nn.leaky_relu" />
<meta itemprop="path" content="Stable" />
</div>

# tf.nn.leaky_relu

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/nn_ops.py">View source</a>



Compute the Leaky ReLU activation function.

``` python
tf.nn.leaky_relu(
    features,
    alpha=0.2,
    name=None
)
```



<!-- Placeholder for "Used in" -->

Source: [Rectifier Nonlinearities Improve Neural Network Acoustic Models.
AL Maas, AY Hannun, AY Ng - Proc. ICML, 2013]
(https://ai.stanford.edu/~amaas/papers/relu_hybrid_icml2013_final.pdf).
Args:
  features: A `Tensor` representing preactivation values. Must be one of
    the following types: `float16`, `float32`, `float64`, `int32`, `int64`.
  alpha: Slope of the activation function at x < 0.
  name: A name for the operation (optional).

#### Returns:

The activation value.



#### References:

Rectifier Nonlinearities Improve Neural Network Acoustic Models:
  [Maas et al., 2013]
  (http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.693.1422)
  ([pdf]
  (http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.693.1422&rep=rep1&type=pdf))


## Compat aliases

* `tf.compat.v1.nn.leaky_relu`
* `tf.compat.v2.nn.leaky_relu`

