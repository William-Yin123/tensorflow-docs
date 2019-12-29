<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.initializers.Identity" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="from_config"/>
<meta itemprop="property" content="get_config"/>
</div>

# tf.keras.initializers.Identity

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/init_ops_v2.py">View source</a>



## Class `Identity`

Initializer that generates the identity matrix.

Inherits From: [`Initializer`](../../../tf/keras/initializers/Initializer.md)

**Aliases**: `tf.initializers.Identity`, `tf.initializers.identity`, `tf.keras.initializers.identity`

<!-- Placeholder for "Used in" -->

Initializers allow you to pre-specify an initialization strategy, encoded in
the Initializer object, without knowing the shape and dtype of the variable
being initialized.

Only usable for generating 2D matrices.

#### Examples:



```
>>> def make_variable(k, initializer):
...   return tf.Variable(initializer(shape=[k, k], dtype=tf.float32))
>>> make_variable(2, tf.initializers.Identity())
<tf.Variable ... shape=(2, 2) dtype=float32, numpy=
array([[1., 0.],
       [0., 1.]], dtype=float32)>
>>> make_variable(3, tf.initializers.Identity(gain=0.5))
<tf.Variable ... shape=(3, 3) dtype=float32, numpy=
array([[0.5, 0. , 0. ],
       [0. , 0.5, 0. ],
       [0. , 0. , 0.5]], dtype=float32)>
```

#### Args:


* <b>`gain`</b>: Multiplicative factor to apply to the identity matrix.

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/ops/init_ops_v2.py">View source</a>

``` python
__init__(gain=1.0)
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
* <b>`ValueError`</b>: If the requested shape does not have exactly two axes.

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

* `tf.compat.v2.initializers.Identity`
* `tf.compat.v2.initializers.identity`
* `tf.compat.v2.keras.initializers.Identity`
* `tf.compat.v2.keras.initializers.identity`

