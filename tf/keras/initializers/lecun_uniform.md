<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.initializers.lecun_uniform" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.initializers.lecun_uniform

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/init_ops_v2.py">View source</a>



LeCun uniform initializer.

**Aliases**: `tf.initializers.lecun_uniform`

``` python
tf.keras.initializers.lecun_uniform(seed=None)
```



<!-- Placeholder for "Used in" -->

Initializers allow you to pre-specify an initialization strategy, encoded in
the Initializer object, without knowing the shape and dtype of the variable
being initialized.

Draws samples from a uniform distribution within [-limit, limit] where `limit`
is `sqrt(3 / fan_in)` where `fan_in` is the number of input units in the
weight tensor.

#### Examples:



```
>>> def make_variables(k, initializer):
...   return (tf.Variable(initializer(shape=[k, k], dtype=tf.float32)),
...           tf.Variable(initializer(shape=[k, k, k], dtype=tf.float32)))
>>> v1, v2 = make_variables(3, tf.initializers.lecun_uniform())
>>> v1
<tf.Variable ... shape=(3, 3) ...
>>> v2
<tf.Variable ... shape=(3, 3, 3) ...
>>> make_variables(4, tf.initializers.RandomNormal())
(<tf.Variable ... shape=(4, 4) dtype=float32...
 <tf.Variable ... shape=(4, 4, 4) dtype=float32...
```

#### Arguments:


* <b>`seed`</b>: A Python integer. Used to seed the random generator.


#### Returns:

A callable Initializer with `shape` and `dtype` arguments which generates a
tensor.



#### References:

- Self-Normalizing Neural Networks,
[Klambauer et al., 2017](https://papers.nips.cc/paper/6698-self-normalizing-neural-networks) # pylint: disable=line-too-long
([pdf](https://papers.nips.cc/paper/6698-self-normalizing-neural-networks.pdf))
- Efficient Backprop,
[Lecun et al., 1998](http://yann.lecun.com/exdb/publis/pdf/lecun-98b.pdf)


## Compat aliases

* `tf.compat.v2.initializers.lecun_uniform`
* `tf.compat.v2.keras.initializers.lecun_uniform`

