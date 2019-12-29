<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.Activation" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
</div>

# tf.keras.layers.Activation

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/core.py">View source</a>



## Class `Activation`

Applies an activation function to an output.

Inherits From: [`Layer`](../../../tf/keras/layers/Layer.md)

<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`activation`</b>: Activation function, such as <a href="../../../tf/nn/relu.md"><code>tf.nn.relu</code></a>, or string name of
  built-in activation function, such as "relu".


#### Input shape:

Arbitrary. Use the keyword argument `input_shape`
(tuple of integers, does not include the samples axis)
when using this layer as the first layer in a model.



#### Output shape:

Same shape as input.


<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/core.py">View source</a>

``` python
__init__(
    activation,
    **kwargs
)
```








## Compat aliases

* `tf.compat.v1.keras.layers.Activation`
* `tf.compat.v2.keras.layers.Activation`

