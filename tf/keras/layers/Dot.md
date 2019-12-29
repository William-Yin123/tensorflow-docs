<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.Dot" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
</div>

# tf.keras.layers.Dot

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/merge.py">View source</a>



## Class `Dot`

Layer that computes a dot product between samples in two tensors.



<!-- Placeholder for "Used in" -->

E.g. if applied to a list of two tensors `a` and `b` of shape
`(batch_size, n)`, the output will be a tensor of shape `(batch_size, 1)`
where each entry `i` will be the dot product between
`a[i]` and `b[i]`.

#### Arguments:


* <b>`axes`</b>: Integer or tuple of integers,
    axis or axes along which to take the dot product.
* <b>`normalize`</b>: Whether to L2-normalize samples along the
    dot product axis before taking the dot product.
    If set to True, then the output of the dot product
    is the cosine proximity between the two samples.
* <b>`**kwargs`</b>: Standard layer keyword arguments.

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/merge.py">View source</a>

``` python
__init__(
    axes,
    normalize=False,
    **kwargs
)
```








## Compat aliases

* `tf.compat.v1.keras.layers.Dot`
* `tf.compat.v2.keras.layers.Dot`

