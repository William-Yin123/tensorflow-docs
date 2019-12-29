<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.initializers.Orthogonal" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="from_config"/>
<meta itemprop="property" content="get_config"/>
</div>

# tf.keras.initializers.Orthogonal

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/init_ops_v2.py">View source</a>



## Class `Orthogonal`

Initializer that generates an orthogonal matrix.

Inherits From: [`Initializer`](../../../tf/keras/initializers/Initializer.md)

**Aliases**: `tf.initializers.Orthogonal`, `tf.initializers.orthogonal`, `tf.keras.initializers.orthogonal`

<!-- Placeholder for "Used in" -->

Initializers allow you to pre-specify an initialization strategy, encoded in
the Initializer object, without knowing the shape and dtype of the variable
being initialized.

If the shape of the tensor to initialize is two-dimensional, it is initialized
with an orthogonal matrix obtained from the QR decomposition of a matrix of
random numbers drawn from a normal distribution.
If the matrix has fewer rows than columns then the output will have orthogonal
rows. Otherwise, the output will have orthogonal columns.

If the shape of the tensor to initialize is more than two-dimensional,
a matrix of shape `(shape[0] * ... * shape[n - 2], shape[n - 1])`
is initialized, where `n` is the length of the shape vector.
The matrix is subsequently reshaped to give a tensor of the desired shape.

#### Examples:



```
>>> def make_variables(k, initializer):
...   return (tf.Variable(initializer(shape=[k, k], dtype=tf.float32)),
...           tf.Variable(initializer(shape=[k, k, k], dtype=tf.float32)))
>>> v1, v2 = make_variables(3, tf.initializers.Orthogonal())
>>> v1
<tf.Variable ... shape=(3, 3) ...
>>> v2
<tf.Variable ... shape=(3, 3, 3) ...
>>> make_variables(4, tf.initializers.Orthogonal(gain=0.5))
(<tf.Variable ... shape=(4, 4) dtype=float32...
 <tf.Variable ... shape=(4, 4, 4) dtype=float32...
```

#### Args:


* <b>`gain`</b>: multiplicative factor to apply to the orthogonal matrix
* <b>`seed`</b>: A Python integer. Used to create random seeds. See
  <a href="../../../tf/random/set_seed.md"><code>tf.random.set_seed</code></a> for behavior.


#### References:

[Saxe et al., 2014](https://openreview.net/forum?id=_wzZwKpTDF_9C)
([pdf](https://arxiv.org/pdf/1312.6120.pdf))


<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/ops/init_ops_v2.py">View source</a>

``` python
__init__(
    gain=1.0,
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


* <b>`ValueError`</b>: If the dtype is not floating point or the input shape is not
 valid.

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

* `tf.compat.v2.initializers.Orthogonal`
* `tf.compat.v2.initializers.orthogonal`
* `tf.compat.v2.keras.initializers.Orthogonal`
* `tf.compat.v2.keras.initializers.orthogonal`

