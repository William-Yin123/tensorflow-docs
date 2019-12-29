<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.Concatenate" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
</div>

# tf.keras.layers.Concatenate

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/merge.py">View source</a>



## Class `Concatenate`

Layer that concatenates a list of inputs.



<!-- Placeholder for "Used in" -->

It takes as input a list of tensors,
all of the same shape except for the concatenation axis,
and returns a single tensor, the concatenation of all inputs.

#### Arguments:


* <b>`axis`</b>: Axis along which to concatenate.
* <b>`**kwargs`</b>: standard layer keyword arguments.

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/merge.py">View source</a>

``` python
__init__(
    axis=-1,
    **kwargs
)
```








## Compat aliases

* `tf.compat.v1.keras.layers.Concatenate`
* `tf.compat.v2.keras.layers.Concatenate`

