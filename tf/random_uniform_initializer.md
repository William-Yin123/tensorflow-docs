<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.random_uniform_initializer" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="from_config"/>
<meta itemprop="property" content="get_config"/>
</div>

# tf.random_uniform_initializer

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/init_ops_v2.py">View source</a>



## Class `random_uniform_initializer`

Initializer that generates tensors with a uniform distribution.

Inherits From: [`Initializer`](../tf/keras/initializers/Initializer.md)

**Aliases**: `tf.initializers.RandomUniform`, `tf.keras.initializers.RandomUniform`

<!-- Placeholder for "Used in" -->

Initializers allow you to pre-specify an initialization strategy, encoded in
the Initializer object, without knowing the shape and dtype of the variable
being initialized.

#### Examples:



```
>>> def make_variables(k, initializer):
...   return (tf.Variable(initializer(shape=[k], dtype=tf.float32)),
...           tf.Variable(initializer(shape=[k, k], dtype=tf.float32)))
>>> v1, v2 = make_variables(3, tf.ones_initializer())
>>> v1
<tf.Variable ... shape=(3,) ... numpy=array([1., 1., 1.], dtype=float32)>
>>> v2
<tf.Variable ... shape=(3, 3) ... numpy=
array([[1., 1., 1.],
       [1., 1., 1.],
       [1., 1., 1.]], dtype=float32)>
>>> make_variables(4, tf.random_uniform_initializer(minval=-1., maxval=1.))
(<tf.Variable...shape=(4,) dtype=float32...>, <tf.Variable...shape=(4, 4) ...
```

#### Args:


* <b>`minval`</b>: A python scalar or a scalar tensor. Lower bound of the range of
  random values to generate (inclusive).
* <b>`maxval`</b>: A python scalar or a scalar tensor. Upper bound of the range of
  random values to generate (exclusive).
* <b>`seed`</b>: A Python integer. Used to create random seeds. See
  <a href="../tf/random/set_seed.md"><code>tf.random.set_seed</code></a> for behavior.

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/ops/init_ops_v2.py">View source</a>

``` python
__init__(
    minval=-0.05,
    maxval=0.05,
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
* <b>`dtype`</b>: Optional dtype of the tensor. Only floating point and integer
types are supported.


#### Raises:


* <b>`ValueError`</b>: If the dtype is not numeric.

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

* `tf.compat.v2.initializers.RandomUniform`
* `tf.compat.v2.keras.initializers.RandomUniform`
* `tf.compat.v2.random_uniform_initializer`

