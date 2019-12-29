<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.depthwise_conv2d" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.depthwise_conv2d

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



2D convolution with separable filters.

``` python
tf.keras.backend.depthwise_conv2d(
    x,
    depthwise_kernel,
    strides=(1, 1),
    padding='valid',
    data_format=None,
    dilation_rate=(1, 1)
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`x`</b>: input tensor
* <b>`depthwise_kernel`</b>: convolution kernel for the depthwise convolution.
* <b>`strides`</b>: strides tuple (length 2).
* <b>`padding`</b>: string, `"same"` or `"valid"`.
* <b>`data_format`</b>: string, `"channels_last"` or `"channels_first"`.
* <b>`dilation_rate`</b>: tuple of integers,
    dilation rates for the separable convolution.


#### Returns:

Output tensor.



#### Raises:


* <b>`ValueError`</b>: if `data_format` is neither `channels_last` or
`channels_first`.

## Compat aliases

* `tf.compat.v1.keras.backend.depthwise_conv2d`
* `tf.compat.v2.keras.backend.depthwise_conv2d`

