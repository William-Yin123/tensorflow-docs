<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.random_normal" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.random_normal

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Returns a tensor with normal distribution of values.

``` python
tf.keras.backend.random_normal(
    shape,
    mean=0.0,
    stddev=1.0,
    dtype=None,
    seed=None
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`shape`</b>: A tuple of integers, the shape of tensor to create.
* <b>`mean`</b>: A float, mean of the normal distribution to draw samples.
* <b>`stddev`</b>: A float, standard deviation of the normal distribution
    to draw samples.
* <b>`dtype`</b>: String, dtype of returned tensor.
* <b>`seed`</b>: Integer, random seed.


#### Returns:

A tensor.


## Compat aliases

* `tf.compat.v1.keras.backend.random_normal`
* `tf.compat.v2.keras.backend.random_normal`

