<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.layers.Dropout" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="graph"/>
<meta itemprop="property" content="scope_name"/>
<meta itemprop="property" content="__init__"/>
</div>

# tf.compat.v1.layers.Dropout

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/layers/core.py">View source</a>



## Class `Dropout`

Applies Dropout to the input.

Inherits From: [`Dropout`](../../../../tf/keras/layers/Dropout.md), [`Layer`](../../../../tf/compat/v1/layers/Layer.md)

<!-- Placeholder for "Used in" -->

Dropout consists in randomly setting a fraction `rate` of input units to 0
at each update during training time, which helps prevent overfitting.
The units that are kept are scaled by `1 / (1 - rate)`, so that their
sum is unchanged at training time and inference time.

#### Arguments:


* <b>`rate`</b>: The dropout rate, between 0 and 1. E.g. `rate=0.1` would drop out
  10% of input units.
* <b>`noise_shape`</b>: 1D tensor of type `int32` representing the shape of the
  binary dropout mask that will be multiplied with the input.
  For instance, if your inputs have shape
  `(batch_size, timesteps, features)`, and you want the dropout mask
  to be the same for all timesteps, you can use
  `noise_shape=[batch_size, 1, features]`.
* <b>`seed`</b>: A Python integer. Used to create random seeds. See
  <a href="../../../../tf/compat/v1/set_random_seed.md"><code>tf.compat.v1.set_random_seed</code></a>.
  for behavior.
* <b>`name`</b>: The name of the layer (string).

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/layers/core.py">View source</a>

``` python
__init__(
    rate=0.5,
    noise_shape=None,
    seed=None,
    name=None,
    **kwargs
)
```






## Properties

<h3 id="graph"><code>graph</code></h3>

DEPRECATED FUNCTION

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Stop using this property because tf.layers layers no longer track their graph.

<h3 id="scope_name"><code>scope_name</code></h3>








