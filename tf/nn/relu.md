<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.nn.relu" />
<meta itemprop="path" content="Stable" />
</div>

# tf.nn.relu

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>



Computes rectified linear: `max(features, 0)`.

``` python
tf.nn.relu(
    features,
    name=None
)
```



<!-- Placeholder for "Used in" -->

See: https://en.wikipedia.org/wiki/Rectifier_(neural_networks)
Example usage:
>>> tf.nn.relu([-2., 0., -0., 3.]).numpy()
array([ 0.,  0., -0.,  3.], dtype=float32)

#### Args:


* <b>`features`</b>: A `Tensor`. Must be one of the following types: `float32`, `float64`, `int32`, `uint8`, `int16`, `int8`, `int64`, `bfloat16`, `uint16`, `half`, `uint32`, `uint64`, `qint8`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `features`.


## Compat aliases

* `tf.compat.v1.nn.relu`
* `tf.compat.v2.nn.relu`

