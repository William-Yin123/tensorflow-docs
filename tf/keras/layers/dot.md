<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.dot" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.layers.dot

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/merge.py">View source</a>



Functional interface to the `Dot` layer.

``` python
tf.keras.layers.dot(
    inputs,
    axes,
    normalize=False,
    **kwargs
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`inputs`</b>: A list of input tensors (at least 2).
* <b>`axes`</b>: Integer or tuple of integers,
    axis or axes along which to take the dot product.
* <b>`normalize`</b>: Whether to L2-normalize samples along the
    dot product axis before taking the dot product.
    If set to True, then the output of the dot product
    is the cosine proximity between the two samples.
* <b>`**kwargs`</b>: Standard layer keyword arguments.


#### Returns:

A tensor, the dot product of the samples from the inputs.


## Compat aliases

* `tf.compat.v1.keras.layers.dot`
* `tf.compat.v2.keras.layers.dot`

