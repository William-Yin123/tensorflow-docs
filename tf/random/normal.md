<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.random.normal" />
<meta itemprop="path" content="Stable" />
</div>

# tf.random.normal

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/random_ops.py">View source</a>



Outputs random values from a normal distribution.

``` python
tf.random.normal(
    shape,
    mean=0.0,
    stddev=1.0,
    dtype=tf.dtypes.float32,
    seed=None,
    name=None
)
```



<!-- Placeholder for "Used in" -->

Example that generates a new set of random values every time:

```
>>> tf.random.set_seed(5);
>>> tf.random.normal([4], 0, 1, tf.float32)
<tf.Tensor: shape=(4,), dtype=float32, numpy=..., dtype=float32)>
```

Example that outputs a reproduceable result:

```
>>> tf.random.set_seed(5);
>>> tf.random.normal([2,2], 0, 1, tf.float32, seed=1)
<tf.Tensor: shape=(2, 2), dtype=float32, numpy=
array([[-1.3768897 , -0.01258316],
      [-0.169515   ,  1.0824056 ]], dtype=float32)>
```

In this case, we are setting both the global and operation-level seed to
ensure this result is reproduceable.  See <a href="../../tf/random/set_seed.md"><code>tf.random.set_seed</code></a> for more
information.

#### Args:


* <b>`shape`</b>: A 1-D integer Tensor or Python array. The shape of the output tensor.
* <b>`mean`</b>: A Tensor or Python value of type `dtype`, broadcastable with `stddev`.
  The mean of the normal distribution.
* <b>`stddev`</b>: A Tensor or Python value of type `dtype`, broadcastable with `mean`.
  The standard deviation of the normal distribution.
* <b>`dtype`</b>: The type of the output.
* <b>`seed`</b>: A Python integer. Used to create a random seed for the distribution.
  See
  <a href="../../tf/random/set_seed.md"><code>tf.random.set_seed</code></a>
  for behavior.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A tensor of the specified shape filled with random normal values.


## Compat aliases

* `tf.compat.v1.random.normal`
* `tf.compat.v1.random_normal`
* `tf.compat.v2.random.normal`

