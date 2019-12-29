<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.ones_initializer" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="from_config"/>
<meta itemprop="property" content="get_config"/>
</div>

# tf.ones_initializer

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/init_ops_v2.py">View source</a>



## Class `ones_initializer`

Initializer that generates tensors initialized to 1.

Inherits From: [`Initializer`](../tf/keras/initializers/Initializer.md)

**Aliases**: `tf.initializers.Ones`, `tf.initializers.ones`, `tf.keras.initializers.Ones`, `tf.keras.initializers.ones`

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
* <b>`dtype`</b>: Optional dtype of the tensor. Only numeric or boolean dtypes are
 supported.


#### Raises:


* <b>`ValuesError`</b>: If the dtype is not numeric or boolean.

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

* `tf.compat.v2.initializers.Ones`
* `tf.compat.v2.initializers.ones`
* `tf.compat.v2.keras.initializers.Ones`
* `tf.compat.v2.keras.initializers.ones`
* `tf.compat.v2.ones_initializer`

