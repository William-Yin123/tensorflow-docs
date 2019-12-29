<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.resize_volumes" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.resize_volumes

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Resizes the volume contained in a 5D tensor.

``` python
tf.keras.backend.resize_volumes(
    x,
    depth_factor,
    height_factor,
    width_factor,
    data_format
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`x`</b>: Tensor or variable to resize.
* <b>`depth_factor`</b>: Positive integer.
* <b>`height_factor`</b>: Positive integer.
* <b>`width_factor`</b>: Positive integer.
* <b>`data_format`</b>: One of `"channels_first"`, `"channels_last"`.


#### Returns:

A tensor.



#### Raises:


* <b>`ValueError`</b>: if `data_format` is neither
    `channels_last` or `channels_first`.

## Compat aliases

* `tf.compat.v1.keras.backend.resize_volumes`
* `tf.compat.v2.keras.backend.resize_volumes`

