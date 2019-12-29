<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.cumsum" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.cumsum

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Cumulative sum of the values in a tensor, alongside the specified axis.

``` python
tf.keras.backend.cumsum(
    x,
    axis=0
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`x`</b>: A tensor or variable.
* <b>`axis`</b>: An integer, the axis to compute the sum.


#### Returns:

A tensor of the cumulative sum of values of `x` along `axis`.


## Compat aliases

* `tf.compat.v1.keras.backend.cumsum`
* `tf.compat.v2.keras.backend.cumsum`

