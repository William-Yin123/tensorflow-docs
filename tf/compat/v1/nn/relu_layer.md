<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.nn.relu_layer" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.nn.relu_layer

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/nn_impl.py">View source</a>



Computes Relu(x * weight + biases).

``` python
tf.compat.v1.nn.relu_layer(
    x,
    weights,
    biases,
    name=None
)
```



<!-- Placeholder for "Used in" -->


#### Args:


* <b>`x`</b>: a 2D tensor.  Dimensions typically: batch, in_units
* <b>`weights`</b>: a 2D tensor.  Dimensions typically: in_units, out_units
* <b>`biases`</b>: a 1D tensor.  Dimensions: out_units
* <b>`name`</b>: A name for the operation (optional).  If not specified
  "nn_relu_layer" is used.


#### Returns:

A 2-D Tensor computing relu(matmul(x, weights) + biases).
Dimensions typically: batch, out_units.


