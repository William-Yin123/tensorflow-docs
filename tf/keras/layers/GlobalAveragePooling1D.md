<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.GlobalAveragePooling1D" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
</div>

# tf.keras.layers.GlobalAveragePooling1D

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/pooling.py">View source</a>



## Class `GlobalAveragePooling1D`

Global average pooling operation for temporal data.



**Aliases**: `tf.keras.layers.GlobalAvgPool1D`

<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`data_format`</b>: A string,
  one of `channels_last` (default) or `channels_first`.
  The ordering of the dimensions in the inputs.
  `channels_last` corresponds to inputs with shape
  `(batch, steps, features)` while `channels_first`
  corresponds to inputs with shape
  `(batch, features, steps)`.


#### Call arguments:


* <b>`inputs`</b>: A 3D tensor.
* <b>`mask`</b>: Binary tensor of shape `(batch_size, steps)` indicating whether
  a given step should be masked (excluded from the average).


#### Input shape:

- If `data_format='channels_last'`:
  3D tensor with shape:
  `(batch_size, steps, features)`
- If `data_format='channels_first'`:
  3D tensor with shape:
  `(batch_size, features, steps)`



#### Output shape:

2D tensor with shape `(batch_size, features)`.


<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/pooling.py">View source</a>

``` python
__init__(
    data_format='channels_last',
    **kwargs
)
```








## Compat aliases

* `tf.compat.v1.keras.layers.GlobalAveragePooling1D`
* `tf.compat.v1.keras.layers.GlobalAvgPool1D`
* `tf.compat.v2.keras.layers.GlobalAveragePooling1D`
* `tf.compat.v2.keras.layers.GlobalAvgPool1D`

