<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.temporal_padding" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.temporal_padding

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Pads the middle dimension of a 3D tensor.

``` python
tf.keras.backend.temporal_padding(
    x,
    padding=(1, 1)
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`x`</b>: Tensor or variable.
* <b>`padding`</b>: Tuple of 2 integers, how many zeros to
    add at the start and end of dim 1.


#### Returns:

A padded 3D tensor.


## Compat aliases

* `tf.compat.v1.keras.backend.temporal_padding`
* `tf.compat.v2.keras.backend.temporal_padding`

