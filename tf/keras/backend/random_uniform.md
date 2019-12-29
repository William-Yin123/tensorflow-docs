<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.random_uniform" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.random_uniform

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Returns a tensor with uniform distribution of values.

``` python
tf.keras.backend.random_uniform(
    shape,
    minval=0.0,
    maxval=1.0,
    dtype=None,
    seed=None
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`shape`</b>: A tuple of integers, the shape of tensor to create.
* <b>`minval`</b>: A float, lower boundary of the uniform distribution
    to draw samples.
* <b>`maxval`</b>: A float, upper boundary of the uniform distribution
    to draw samples.
* <b>`dtype`</b>: String, dtype of returned tensor.
* <b>`seed`</b>: Integer, random seed.


#### Returns:

A tensor.


## Compat aliases

* `tf.compat.v1.keras.backend.random_uniform`
* `tf.compat.v2.keras.backend.random_uniform`

