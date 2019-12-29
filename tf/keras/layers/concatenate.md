<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.concatenate" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.layers.concatenate

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/merge.py">View source</a>



Functional interface to the `Concatenate` layer.

``` python
tf.keras.layers.concatenate(
    inputs,
    axis=-1,
    **kwargs
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`inputs`</b>: A list of input tensors (at least 2).
* <b>`axis`</b>: Concatenation axis.
* <b>`**kwargs`</b>: Standard layer keyword arguments.


#### Returns:

A tensor, the concatenation of the inputs alongside axis `axis`.


## Compat aliases

* `tf.compat.v1.keras.layers.concatenate`
* `tf.compat.v2.keras.layers.concatenate`

