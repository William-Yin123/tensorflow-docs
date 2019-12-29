<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.nn.relu6" />
<meta itemprop="path" content="Stable" />
</div>

# tf.nn.relu6

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/nn_ops.py">View source</a>



Computes Rectified Linear 6: `min(max(features, 0), 6)`.

``` python
tf.nn.relu6(
    features,
    name=None
)
```



<!-- Placeholder for "Used in" -->


#### Args:


* <b>`features`</b>: A `Tensor` with type `float`, `double`, `int32`, `int64`, `uint8`,
  `int16`, or `int8`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` with the same type as `features`.



#### References:

Convolutional Deep Belief Networks on CIFAR-10:
  Krizhevsky et al., 2010
  ([pdf](http://www.cs.utoronto.ca/~kriz/conv-cifar10-aug2010.pdf))


## Compat aliases

* `tf.compat.v1.nn.relu6`
* `tf.compat.v2.nn.relu6`

