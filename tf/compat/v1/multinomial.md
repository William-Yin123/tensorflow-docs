<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.multinomial" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.multinomial

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/random_ops.py">View source</a>



Draws samples from a multinomial distribution. (deprecated)

``` python
tf.compat.v1.multinomial(
    logits,
    num_samples,
    seed=None,
    name=None,
    output_dtype=None
)
```



<!-- Placeholder for "Used in" -->

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Use <a href="../../../tf/random/categorical.md"><code>tf.random.categorical</code></a> instead.

#### Example:



```python
# samples has shape [1, 5], where each value is either 0 or 1 with equal
# probability.
samples = tf.random.categorical(tf.math.log([[0.5, 0.5]]), 5)
```

#### Args:


* <b>`logits`</b>: 2-D Tensor with shape `[batch_size, num_classes]`.  Each slice
  `[i, :]` represents the unnormalized log-probabilities for all classes.
* <b>`num_samples`</b>: 0-D.  Number of independent samples to draw for each row slice.
* <b>`seed`</b>: A Python integer. Used to create a random seed for the distribution.
  See <a href="../../../tf/random/set_seed.md"><code>tf.random.set_seed</code></a> for behavior.
* <b>`name`</b>: Optional name for the operation.
* <b>`output_dtype`</b>: integer type to use for the output. Defaults to int64.


#### Returns:

The drawn samples of shape `[batch_size, num_samples]`.


## Compat aliases

* `tf.compat.v1.random.multinomial`

