<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.dropout" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.dropout

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Sets entries in `x` to zero at random, while scaling the entire tensor.

``` python
tf.keras.backend.dropout(
    x,
    level,
    noise_shape=None,
    seed=None
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`x`</b>: tensor
* <b>`level`</b>: fraction of the entries in the tensor
    that will be set to 0.
* <b>`noise_shape`</b>: shape for randomly generated keep/drop flags,
    must be broadcastable to the shape of `x`
* <b>`seed`</b>: random seed to ensure determinism.


#### Returns:

A tensor.


## Compat aliases

* `tf.compat.v1.keras.backend.dropout`
* `tf.compat.v2.keras.backend.dropout`

