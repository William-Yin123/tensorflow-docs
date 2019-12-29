<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.bias_add" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.bias_add

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Adds a bias vector to a tensor.

``` python
tf.keras.backend.bias_add(
    x,
    bias,
    data_format=None
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`x`</b>: Tensor or variable.
* <b>`bias`</b>: Bias tensor to add.
* <b>`data_format`</b>: string, `"channels_last"` or `"channels_first"`.


#### Returns:

Output tensor.



#### Raises:


* <b>`ValueError`</b>: In one of the two cases below:
            1. invalid `data_format` argument.
            2. invalid bias shape.
               the bias should be either a vector or
               a tensor with ndim(x) - 1 dimension

## Compat aliases

* `tf.compat.v1.keras.backend.bias_add`
* `tf.compat.v2.keras.backend.bias_add`

