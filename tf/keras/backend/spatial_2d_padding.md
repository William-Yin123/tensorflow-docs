<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.spatial_2d_padding" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.spatial_2d_padding

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Pads the 2nd and 3rd dimensions of a 4D tensor.

``` python
tf.keras.backend.spatial_2d_padding(
    x,
    padding=((1, 1), (1, 1)),
    data_format=None
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`x`</b>: Tensor or variable.
* <b>`padding`</b>: Tuple of 2 tuples, padding pattern.
* <b>`data_format`</b>: One of `channels_last` or `channels_first`.


#### Returns:

A padded 4D tensor.



#### Raises:


* <b>`ValueError`</b>: if `data_format` is neither
    `channels_last` or `channels_first`.

## Compat aliases

* `tf.compat.v1.keras.backend.spatial_2d_padding`
* `tf.compat.v2.keras.backend.spatial_2d_padding`

