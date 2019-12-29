<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.local_conv1d" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.local_conv1d

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Apply 1D conv with un-shared weights.

``` python
tf.keras.backend.local_conv1d(
    inputs,
    kernel,
    kernel_size,
    strides,
    data_format=None
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`inputs`</b>: 3D tensor with shape:
    (batch_size, steps, input_dim)
    if data_format is "channels_last" or
    (batch_size, input_dim, steps)
    if data_format is "channels_first".
* <b>`kernel`</b>: the unshared weight for convolution,
    with shape (output_length, feature_dim, filters).
* <b>`kernel_size`</b>: a tuple of a single integer,
    specifying the length of the 1D convolution window.
* <b>`strides`</b>: a tuple of a single integer,
    specifying the stride length of the convolution.
* <b>`data_format`</b>: the data format, channels_first or channels_last.


#### Returns:

A 3d tensor with shape:
(batch_size, output_length, filters)
if data_format='channels_first'
or 3D tensor with shape:
(batch_size, filters, output_length)
if data_format='channels_last'.


## Compat aliases

* `tf.compat.v1.keras.backend.local_conv1d`
* `tf.compat.v2.keras.backend.local_conv1d`

