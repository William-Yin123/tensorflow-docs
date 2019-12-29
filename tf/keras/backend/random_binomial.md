<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.random_binomial" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.random_binomial

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Returns a tensor with random binomial distribution of values.

``` python
tf.keras.backend.random_binomial(
    shape,
    p=0.0,
    dtype=None,
    seed=None
)
```



<!-- Placeholder for "Used in" -->

The binomial distribution with parameters `n` and `p` is the probability
distribution of the number of successful Bernoulli process. Only supports
`n` = 1 for now.

#### Arguments:


* <b>`shape`</b>: A tuple of integers, the shape of tensor to create.
* <b>`p`</b>: A float, `0. <= p <= 1`, probability of binomial distribution.
* <b>`dtype`</b>: String, dtype of returned tensor.
* <b>`seed`</b>: Integer, random seed.


#### Returns:

A tensor.


## Compat aliases

* `tf.compat.v1.keras.backend.random_binomial`
* `tf.compat.v2.keras.backend.random_binomial`

