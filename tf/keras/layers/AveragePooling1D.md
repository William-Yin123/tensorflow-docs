<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.AveragePooling1D" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
</div>

# tf.keras.layers.AveragePooling1D

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/pooling.py">View source</a>



## Class `AveragePooling1D`

Average pooling for temporal data.



**Aliases**: `tf.keras.layers.AvgPool1D`

<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`pool_size`</b>: Integer, size of the average pooling windows.
* <b>`strides`</b>: Integer, or None. Factor by which to downscale.
  E.g. 2 will halve the input.
  If None, it will default to `pool_size`.
* <b>`padding`</b>: One of `"valid"` or `"same"` (case-insensitive).
* <b>`data_format`</b>: A string,
  one of `channels_last` (default) or `channels_first`.
  The ordering of the dimensions in the inputs.
  `channels_last` corresponds to inputs with shape
  `(batch, steps, features)` while `channels_first`
  corresponds to inputs with shape
  `(batch, features, steps)`.


#### Input shape:

- If `data_format='channels_last'`:
  3D tensor with shape `(batch_size, steps, features)`.
- If `data_format='channels_first'`:
  3D tensor with shape `(batch_size, features, steps)`.



#### Output shape:

- If `data_format='channels_last'`:
  3D tensor with shape `(batch_size, downsampled_steps, features)`.
- If `data_format='channels_first'`:
  3D tensor with shape `(batch_size, features, downsampled_steps)`.


<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/pooling.py">View source</a>

``` python
__init__(
    pool_size=2,
    strides=None,
    padding='valid',
    data_format='channels_last',
    **kwargs
)
```








## Compat aliases

* `tf.compat.v1.keras.layers.AveragePooling1D`
* `tf.compat.v1.keras.layers.AvgPool1D`
* `tf.compat.v2.keras.layers.AveragePooling1D`
* `tf.compat.v2.keras.layers.AvgPool1D`

