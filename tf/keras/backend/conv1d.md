<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.conv1d" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.conv1d

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



1D convolution.

``` python
tf.keras.backend.conv1d(
    x,
    kernel,
    strides=1,
    padding='valid',
    data_format=None,
    dilation_rate=1
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`x`</b>: Tensor or variable.
* <b>`kernel`</b>: kernel tensor.
* <b>`strides`</b>: stride integer.
* <b>`padding`</b>: string, `"same"`, `"causal"` or `"valid"`.
* <b>`data_format`</b>: string, one of "channels_last", "channels_first".
* <b>`dilation_rate`</b>: integer dilate rate.


#### Returns:

A tensor, result of 1D convolution.



#### Raises:


* <b>`ValueError`</b>: if `data_format` is neither `channels_last` or
`channels_first`.

## Compat aliases

* `tf.compat.v1.keras.backend.conv1d`
* `tf.compat.v2.keras.backend.conv1d`

