<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.cumprod" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.cumprod

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Cumulative product of the values in a tensor, alongside the specified axis.

``` python
tf.keras.backend.cumprod(
    x,
    axis=0
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`x`</b>: A tensor or variable.
* <b>`axis`</b>: An integer, the axis to compute the product.


#### Returns:

A tensor of the cumulative product of values of `x` along `axis`.


## Compat aliases

* `tf.compat.v1.keras.backend.cumprod`
* `tf.compat.v2.keras.backend.cumprod`

