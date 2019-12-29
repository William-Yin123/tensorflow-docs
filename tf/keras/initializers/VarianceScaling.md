<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.initializers.VarianceScaling" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="from_config"/>
<meta itemprop="property" content="get_config"/>
</div>

# tf.keras.initializers.VarianceScaling

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/init_ops_v2.py">View source</a>



## Class `VarianceScaling`

Initializer capable of adapting its scale to the shape of weights tensors.

Inherits From: [`Initializer`](../../../tf/keras/initializers/Initializer.md)

**Aliases**: `tf.initializers.VarianceScaling`

<!-- Placeholder for "Used in" -->

Initializers allow you to pre-specify an initialization strategy, encoded in
the Initializer object, without knowing the shape and dtype of the variable
being initialized.

With `distribution="truncated_normal" or "untruncated_normal"`, samples are
drawn from a truncated/untruncated normal distribution with a mean of zero and
a standard deviation (after truncation, if used) `stddev = sqrt(scale / n)`
where n is:

  - number of input units in the weight tensor, if mode = "fan_in"
  - number of output units, if mode = "fan_out"
  - average of the numbers of input and output units, if mode = "fan_avg"

With `distribution="uniform"`, samples are drawn from a uniform distribution
within [-limit, limit], with `limit = sqrt(3 * scale / n)`.

#### Examples:



```
>>> def make_variables(k, initializer):
...   return (tf.Variable(initializer(shape=[k], dtype=tf.float32)),
...           tf.Variable(initializer(shape=[k, k], dtype=tf.float32)))
>>> v1, v2 = make_variables(3, tf.initializers.VarianceScaling(scale=1.))
>>> v1
<tf.Variable ... shape=(3,) ... numpy=array([...], dtype=float32)>
>>> v2
<tf.Variable ... shape=(3, 3) ... numpy=
...
>>> make_variables(4, tf.initializers.VarianceScaling(distribution='uniform'))
(<tf.Variable...shape=(4,) dtype=float32...>, <tf.Variable...shape=(4, 4) ...
```

#### Args:


* <b>`scale`</b>: Scaling factor (positive float).
* <b>`mode`</b>: One of "fan_in", "fan_out", "fan_avg".
* <b>`distribution`</b>: Random distribution to use. One of "truncated_normal",
  "untruncated_normal" and  "uniform".
* <b>`seed`</b>: A Python integer. Used to create random seeds. See
  <a href="../../../tf/random/set_seed.md"><code>tf.random.set_seed</code></a> for behavior.


#### Raises:


* <b>`ValueError`</b>: In case of an invalid value for the "scale", mode" or
  "distribution" arguments.

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/ops/init_ops_v2.py">View source</a>

``` python
__init__(
    scale=1.0,
    mode='fan_in',
    distribution='truncated_normal',
    seed=None
)
```

Initialize self.  See help(type(self)) for accurate signature.




## Methods

<h3 id="__call__"><code>__call__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/init_ops_v2.py">View source</a>

``` python
__call__(
    shape,
    dtype=tf.dtypes.float32
)
```

Returns a tensor object initialized as specified by the initializer.


#### Args:


* <b>`shape`</b>: Shape of the tensor.
* <b>`dtype`</b>: Optional dtype of the tensor. Only floating point types are
 supported.


#### Raises:


* <b>`ValueError`</b>: If the dtype is not floating point

<h3 id="from_config"><code>from_config</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/init_ops_v2.py">View source</a>

``` python
from_config(
    cls,
    config
)
```

Instantiates an initializer from a configuration dictionary.


#### Example:



```python
initializer = RandomUniform(-1, 1)
config = initializer.get_config()
initializer = RandomUniform.from_config(config)
```

#### Args:


* <b>`config`</b>: A Python dictionary.
  It will typically be the output of `get_config`.


#### Returns:

An Initializer instance.


<h3 id="get_config"><code>get_config</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/init_ops_v2.py">View source</a>

``` python
get_config()
```

Returns the configuration of the initializer as a JSON-serializable dict.


#### Returns:

A JSON-serializable Python dict.






## Compat aliases

* `tf.compat.v2.initializers.VarianceScaling`
* `tf.compat.v2.keras.initializers.VarianceScaling`

