<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.constant_initializer" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="from_config"/>
<meta itemprop="property" content="get_config"/>
</div>

# tf.constant_initializer

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/init_ops_v2.py">View source</a>



## Class `constant_initializer`

Initializer that generates tensors with constant values.

Inherits From: [`Initializer`](../tf/keras/initializers/Initializer.md)

**Aliases**: `tf.initializers.Constant`, `tf.initializers.constant`, `tf.keras.initializers.Constant`, `tf.keras.initializers.constant`

<!-- Placeholder for "Used in" -->

Initializers allow you to pre-specify an initialization strategy, encoded in
the Initializer object, without knowing the shape and dtype of the variable
being initialized.

<a href="../tf/constant_initializer.md"><code>tf.constant_initializer</code></a> returns an object which when called returns a tensor
populated with the `value` specified in the constructor. This `value` must be
convertible to the requested `dtype`.

The argument `value` can be a scalar constant value, or a list of
values. Scalars broadcast to whichever shape is requested from the
initializer.

If `value` is a list, then the length of the list must be equal to the number
of elements implied by the desired shape of the tensor. If the total number of
elements in `value` is not equal to the number of elements required by the
tensor shape, the initializer will raise a `TypeError`.

#### Examples:



```
>>> def make_variables(k, initializer):
...   return (tf.Variable(initializer(shape=[k], dtype=tf.float32)),
...           tf.Variable(initializer(shape=[k, k], dtype=tf.float32)))
>>> v1, v2 = make_variables(3, tf.constant_initializer(2.))
>>> v1
<tf.Variable ... shape=(3,) ... numpy=array([2., 2., 2.], dtype=float32)>
>>> v2
<tf.Variable ... shape=(3, 3) ... numpy=
array([[2., 2., 2.],
       [2., 2., 2.],
       [2., 2., 2.]], dtype=float32)>
>>> make_variables(4, tf.random_uniform_initializer(minval=-1., maxval=1.))
(<tf.Variable...shape=(4,) dtype=float32...>, <tf.Variable...shape=(4, 4) ...
```

```
>>> value = [0, 1, 2, 3, 4, 5, 6, 7]
>>> init = tf.constant_initializer(value)
>>> # Fitting shape
>>> tf.Variable(init(shape=[2, 4], dtype=tf.float32))
<tf.Variable ...
array([[0., 1., 2., 3.],
       [4., 5., 6., 7.]], dtype=float32)>
>>> # Larger shape
>>> tf.Variable(init(shape=[3, 4], dtype=tf.float32))
Traceback (most recent call last):
...
TypeError: ...value has 8 elements, shape is (3, 4) with 12 elements...
>>> # Smaller shape
>>> tf.Variable(init(shape=[2, 3], dtype=tf.float32))
Traceback (most recent call last):
...
TypeError: ...value has 8 elements, shape is (2, 3) with 6 elements...
```

#### Args:


* <b>`value`</b>: A Python scalar, list or tuple of values, or a N-dimensional numpy
  array. All elements of the initialized variable will be set to the
  corresponding value in the `value` argument.


#### Raises:


* <b>`TypeError`</b>: If the input `value` is not one of the expected types.

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/ops/init_ops_v2.py">View source</a>

``` python
__init__(value=0)
```

Initialize self.  See help(type(self)) for accurate signature.




## Methods

<h3 id="__call__"><code>__call__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/init_ops_v2.py">View source</a>

``` python
__call__(
    shape,
    dtype=None
)
```

Returns a tensor object initialized as specified by the initializer.


#### Args:


* <b>`shape`</b>: Shape of the tensor.
* <b>`dtype`</b>: Optional dtype of the tensor. If not provided the dtype of the
 tensor created will be the type of the inital value.


#### Raises:


* <b>`TypeError`</b>: If the initializer cannot create a tensor of the requested
 dtype.

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

* `tf.compat.v2.constant_initializer`
* `tf.compat.v2.initializers.Constant`
* `tf.compat.v2.initializers.constant`
* `tf.compat.v2.keras.initializers.Constant`
* `tf.compat.v2.keras.initializers.constant`

