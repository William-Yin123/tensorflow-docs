<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.layers.Flatten" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="graph"/>
<meta itemprop="property" content="scope_name"/>
<meta itemprop="property" content="__init__"/>
</div>

# tf.compat.v1.layers.Flatten

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/layers/core.py">View source</a>



## Class `Flatten`

Flattens an input tensor while preserving the batch axis (axis 0).

Inherits From: [`Flatten`](../../../../tf/keras/layers/Flatten.md), [`Layer`](../../../../tf/compat/v1/layers/Layer.md)

<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`data_format`</b>: A string, one of `channels_last` (default) or `channels_first`.
  The ordering of the dimensions in the inputs.
  `channels_last` corresponds to inputs with shape
  `(batch, ..., channels)` while `channels_first` corresponds to
  inputs with shape `(batch, channels, ...)`.


#### Examples:



```
  x = tf.compat.v1.placeholder(shape=(None, 4, 4), dtype='float32')
  y = Flatten()(x)
  # now `y` has shape `(None, 16)`

  x = tf.compat.v1.placeholder(shape=(None, 3, None), dtype='float32')
  y = Flatten()(x)
  # now `y` has shape `(None, None)`
```

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/core.py">View source</a>

``` python
__init__(
    data_format=None,
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








