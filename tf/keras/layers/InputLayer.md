<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.InputLayer" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
</div>

# tf.keras.layers.InputLayer

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/engine/input_layer.py">View source</a>



## Class `InputLayer`

Layer to be used as an entry point into a Network (a graph of layers).

Inherits From: [`Layer`](../../../tf/keras/layers/Layer.md)

<!-- Placeholder for "Used in" -->

It can either wrap an existing tensor (pass an `input_tensor` argument)
or create a placeholder tensor (pass arguments `input_shape`, and
optionally, `dtype`).

It is generally recommend to use the functional layer API via `Input`,
(which creates an `InputLayer`) without directly using `InputLayer`.

This class can create placeholders for tf.Tensors, tf.SparseTensors, and
tf.RaggedTensors by choosing 'sparse=True' or 'ragged=True'.

#### Arguments:


* <b>`input_shape`</b>: Shape tuple (not including the batch axis), or `TensorShape`
  instance (not including the batch axis).
* <b>`batch_size`</b>: Optional input batch size (integer or None).
* <b>`dtype`</b>: Datatype of the input.
* <b>`input_tensor`</b>: Optional tensor to use as layer input
    instead of creating a placeholder.
* <b>`sparse`</b>: Boolean, whether the placeholder created is meant to be sparse.
* <b>`ragged`</b>: Boolean, whether the placeholder created is meant to be ragged.
    In this case, values of 'None' in the 'shape' argument represent
    ragged dimensions. For more information about RaggedTensors, see
    https://www.tensorflow.org/guide/ragged_tensors.
* <b>`name`</b>: Name of the layer (string).

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/engine/input_layer.py">View source</a>

``` python
__init__(
    input_shape=None,
    batch_size=None,
    dtype=None,
    input_tensor=None,
    sparse=False,
    name=None,
    ragged=False,
    **kwargs
)
```








## Compat aliases

* `tf.compat.v1.keras.layers.InputLayer`
* `tf.compat.v2.keras.layers.InputLayer`

