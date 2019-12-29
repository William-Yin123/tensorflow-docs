<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.random.create_rng_state" />
<meta itemprop="path" content="Stable" />
</div>

# tf.random.create_rng_state

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/stateful_random_ops.py">View source</a>



Creates a RNG state from an integer or a vector.

**Aliases**: `tf.random.experimental.create_rng_state`

``` python
tf.random.create_rng_state(
    seed,
    alg
)
```



<!-- Placeholder for "Used in" -->


#### Example:



```
>>> tf.random.create_rng_state(
...     1234, "philox")
array([1234,    0,    0])
>>> tf.random.create_rng_state(
...     [12, 34], "threefry")
array([12, 34])
```

#### Args:


* <b>`seed`</b>: an integer or 1-D numpy array.
* <b>`alg`</b>: the RNG algorithm. Can be a string, an `Algorithm` or an integer.


#### Returns:

a 1-D numpy array whose size depends on the algorithm.


## Compat aliases

* `tf.compat.v1.random.create_rng_state`
* `tf.compat.v1.random.experimental.create_rng_state`
* `tf.compat.v2.random.create_rng_state`
* `tf.compat.v2.random.experimental.create_rng_state`

