<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.conv2d_transpose" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.conv2d_transpose

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



2D deconvolution (i.e.

``` python
tf.keras.backend.conv2d_transpose(
    x,
    kernel,
    output_shape,
    strides=(1, 1),
    padding='valid',
    data_format=None,
    dilation_rate=(1, 1)
)
```



<!-- Placeholder for "Used in" -->

transposed convolution).

#### Arguments:


* <b>`x`</b>: Tensor or variable.
* <b>`kernel`</b>: kernel tensor.
* <b>`output_shape`</b>: 1D int tensor for the output shape.
* <b>`strides`</b>: strides tuple.
* <b>`padding`</b>: string, `"same"` or `"valid"`.
* <b>`data_format`</b>: string, `"channels_last"` or `"channels_first"`.
* <b>`dilation_rate`</b>: Tuple of 2 integers.


#### Returns:

A tensor, result of transposed 2D convolution.



#### Raises:


* <b>`ValueError`</b>: if `data_format` is neither `channels_last` or
`channels_first`.

## Compat aliases

* `tf.compat.v1.keras.backend.conv2d_transpose`
* `tf.compat.v2.keras.backend.conv2d_transpose`

