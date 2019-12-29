<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.ThresholdedReLU" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
</div>

# tf.keras.layers.ThresholdedReLU

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/advanced_activations.py">View source</a>



## Class `ThresholdedReLU`

Thresholded Rectified Linear Unit.

Inherits From: [`Layer`](../../../tf/keras/layers/Layer.md)

<!-- Placeholder for "Used in" -->


#### It follows:


`f(x) = x for x > theta`,
`f(x) = 0 otherwise`.

#### Input shape:

Arbitrary. Use the keyword argument `input_shape`
(tuple of integers, does not include the samples axis)
when using this layer as the first layer in a model.



#### Output shape:

Same shape as the input.



#### Arguments:


* <b>`theta`</b>: Float >= 0. Threshold location of activation.

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/advanced_activations.py">View source</a>

``` python
__init__(
    theta=1.0,
    **kwargs
)
```








## Compat aliases

* `tf.compat.v1.keras.layers.ThresholdedReLU`
* `tf.compat.v2.keras.layers.ThresholdedReLU`

