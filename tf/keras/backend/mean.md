<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.mean" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.mean

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Mean of a tensor, alongside the specified axis.

``` python
tf.keras.backend.mean(
    x,
    axis=None,
    keepdims=False
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`x`</b>: A tensor or variable.
* <b>`axis`</b>: A list of integer. Axes to compute the mean.
* <b>`keepdims`</b>: A boolean, whether to keep the dimensions or not.
    If `keepdims` is `False`, the rank of the tensor is reduced
    by 1 for each entry in `axis`. If `keepdims` is `True`,
    the reduced dimensions are retained with length 1.


#### Returns:

A tensor with the mean of elements of `x`.


## Compat aliases

* `tf.compat.v1.keras.backend.mean`
* `tf.compat.v2.keras.backend.mean`

