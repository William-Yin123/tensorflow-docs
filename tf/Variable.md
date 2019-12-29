<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.Variable" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="SaveSliceInfo"/>
<meta itemprop="property" content="aggregation"/>
<meta itemprop="property" content="constraint"/>
<meta itemprop="property" content="device"/>
<meta itemprop="property" content="dtype"/>
<meta itemprop="property" content="graph"/>
<meta itemprop="property" content="initial_value"/>
<meta itemprop="property" content="initializer"/>
<meta itemprop="property" content="name"/>
<meta itemprop="property" content="op"/>
<meta itemprop="property" content="shape"/>
<meta itemprop="property" content="synchronization"/>
<meta itemprop="property" content="trainable"/>
<meta itemprop="property" content="__abs__"/>
<meta itemprop="property" content="__add__"/>
<meta itemprop="property" content="__and__"/>
<meta itemprop="property" content="__div__"/>
<meta itemprop="property" content="__eq__"/>
<meta itemprop="property" content="__floordiv__"/>
<meta itemprop="property" content="__ge__"/>
<meta itemprop="property" content="__getitem__"/>
<meta itemprop="property" content="__gt__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="__invert__"/>
<meta itemprop="property" content="__iter__"/>
<meta itemprop="property" content="__le__"/>
<meta itemprop="property" content="__lt__"/>
<meta itemprop="property" content="__matmul__"/>
<meta itemprop="property" content="__mod__"/>
<meta itemprop="property" content="__mul__"/>
<meta itemprop="property" content="__ne__"/>
<meta itemprop="property" content="__neg__"/>
<meta itemprop="property" content="__or__"/>
<meta itemprop="property" content="__pow__"/>
<meta itemprop="property" content="__radd__"/>
<meta itemprop="property" content="__rand__"/>
<meta itemprop="property" content="__rdiv__"/>
<meta itemprop="property" content="__rfloordiv__"/>
<meta itemprop="property" content="__rmatmul__"/>
<meta itemprop="property" content="__rmod__"/>
<meta itemprop="property" content="__rmul__"/>
<meta itemprop="property" content="__ror__"/>
<meta itemprop="property" content="__rpow__"/>
<meta itemprop="property" content="__rsub__"/>
<meta itemprop="property" content="__rtruediv__"/>
<meta itemprop="property" content="__rxor__"/>
<meta itemprop="property" content="__sub__"/>
<meta itemprop="property" content="__truediv__"/>
<meta itemprop="property" content="__xor__"/>
<meta itemprop="property" content="assign"/>
<meta itemprop="property" content="assign_add"/>
<meta itemprop="property" content="assign_sub"/>
<meta itemprop="property" content="batch_scatter_update"/>
<meta itemprop="property" content="count_up_to"/>
<meta itemprop="property" content="eval"/>
<meta itemprop="property" content="experimental_ref"/>
<meta itemprop="property" content="from_proto"/>
<meta itemprop="property" content="gather_nd"/>
<meta itemprop="property" content="get_shape"/>
<meta itemprop="property" content="initialized_value"/>
<meta itemprop="property" content="load"/>
<meta itemprop="property" content="read_value"/>
<meta itemprop="property" content="scatter_add"/>
<meta itemprop="property" content="scatter_div"/>
<meta itemprop="property" content="scatter_max"/>
<meta itemprop="property" content="scatter_min"/>
<meta itemprop="property" content="scatter_mul"/>
<meta itemprop="property" content="scatter_nd_add"/>
<meta itemprop="property" content="scatter_nd_sub"/>
<meta itemprop="property" content="scatter_nd_update"/>
<meta itemprop="property" content="scatter_sub"/>
<meta itemprop="property" content="scatter_update"/>
<meta itemprop="property" content="set_shape"/>
<meta itemprop="property" content="sparse_read"/>
<meta itemprop="property" content="to_proto"/>
<meta itemprop="property" content="value"/>
</div>

# tf.Variable

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>



## Class `Variable`

See the [variable guide](https://tensorflow.org/guide/variable).



<!-- Placeholder for "Used in" -->

A variable maintains shared, persistent state manipulated by a program.

The `Variable()` constructor requires an initial value for the variable, which
can be a `Tensor` of any type and shape. This initial value defines the type
and shape of the variable. After construction, the type and shape of the
variable are fixed. The value can be changed using one of the assign methods.

```
>>> v = tf.Variable(1.)
>>> v.assign(2.)
<tf.Variable ... shape=() dtype=float32, numpy=2.0>
>>> v.assign_add(0.5)
<tf.Variable ... shape=() dtype=float32, numpy=2.5>
```

The `shape` argument to `Variable`'s constructor allows you to construct a
variable with a less defined shape than its `initial_value`:

```
>>> v = tf.Variable(1., shape=tf.TensorShape(None))
>>> v.assign([[1.]])
<tf.Variable ... shape=<unknown> dtype=float32, numpy=array([[1.]], ...)>
```

Just like any `Tensor`, variables created with `Variable()` can be used as
inputs to operations. Additionally, all the operators overloaded for the
`Tensor` class are carried over to variables.

```
>>> w = tf.Variable([[1.], [2.]])
>>> x = tf.constant([[3., 4.]])
>>> tf.matmul(w, x)
<tf.Tensor:... shape=(2, 2), ... numpy=
  array([[3., 4.],
         [6., 8.]], dtype=float32)>
>>> tf.sigmoid(w + x)
<tf.Tensor:... shape=(2, 2), ...>
```

When building a machine learning model it is often convenient to distinguish
between variables holding trainable model parameters and other variables such
as a `step` variable used to count training steps. To make this easier, the
variable constructor supports a `trainable=<bool>`
parameter. <a href="../tf/GradientTape.md"><code>tf.GradientTape</code></a> watches trainable variables by default:

```
>>> with tf.GradientTape(persistent=True) as tape:
...   trainable = tf.Variable(1.)
...   non_trainable = tf.Variable(2., trainable=False)
...   x1 = trainable * 2.
...   x2 = non_trainable * 3.
>>> tape.gradient(x1, trainable)
<tf.Tensor:... shape=(), dtype=float32, numpy=2.0>
>>> assert tape.gradient(x2, non_trainable) is None  # Unwatched
```

Variables are automatically tracked when assigned to attributes of types
inheriting from <a href="../tf/Module.md"><code>tf.Module</code></a>.

```
>>> m = tf.Module()
>>> m.v = tf.Variable([1.])
>>> m.trainable_variables
(<tf.Variable ... shape=(1,) ... numpy=array([1.], dtype=float32)>,)
```

This tracking then allows saving variable values to
[training checkpoints](https://www.tensorflow.org/guide/checkpoint), or to
[SavedModels](https://www.tensorflow.org/guide/saved_model) which include
serialized TensorFlow graphs.

Variables are often captured and manipulated by <a href="../tf/function.md"><code>tf.function</code></a>s. This works the
same way the un-decorated function would have:

```
>>> v = tf.Variable(0.)
>>> read_and_decrement = tf.function(lambda: v.assign_sub(0.1))
>>> read_and_decrement()
<tf.Tensor: shape=(), dtype=float32, numpy=-0.1>
>>> read_and_decrement()
<tf.Tensor: shape=(), dtype=float32, numpy=-0.2>
```

Variables created inside a <a href="../tf/function.md"><code>tf.function</code></a> must be owned outside the function
and be created only once:

```
>>> class M(tf.Module):
...   @tf.function
...   def __call__(self, x):
...     if not hasattr(self, "v"):  # Or set self.v to None in __init__
...       self.v = tf.Variable(x)
...     return self.v * x
>>> m = M()
>>> m(2.)
<tf.Tensor: shape=(), dtype=float32, numpy=4.0>
>>> m(3.)
<tf.Tensor: shape=(), dtype=float32, numpy=6.0>
>>> m.v
<tf.Variable ... shape=() dtype=float32, numpy=2.0>
```

See the <a href="../tf/function.md"><code>tf.function</code></a> documentation for details.

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
__init__(
    initial_value=None,
    trainable=None,
    validate_shape=True,
    caching_device=None,
    name=None,
    variable_def=None,
    dtype=None,
    import_scope=None,
    constraint=None,
    synchronization=tf.VariableSynchronization.AUTO,
    aggregation=tf.compat.v1.VariableAggregation.NONE,
    shape=None
)
```

Creates a new variable with value `initial_value`. (deprecated arguments)

Warning: SOME ARGUMENTS ARE DEPRECATED: `(caching_device)`. They will be removed in a future version.
Instructions for updating:
A variable's value can be manually cached by calling tf.Variable.read_value() under a tf.device scope. The caching_device argument does not work properly.

#### Args:


* <b>`initial_value`</b>: A `Tensor`, or Python object convertible to a `Tensor`,
  which is the initial value for the Variable. The initial value must have
  a shape specified unless `validate_shape` is set to False. Can also be a
  callable with no argument that returns the initial value when called. In
  that case, `dtype` must be specified. (Note that initializer functions
  from init_ops.py must first be bound to a shape before being used here.)
* <b>`trainable`</b>: If `True`, GradientTapes automatically watch uses of this
  variable. Defaults to `True`, unless `synchronization` is set to
  `ON_READ`, in which case it defaults to `False`.
* <b>`validate_shape`</b>: If `False`, allows the variable to be initialized with a
  value of unknown shape. If `True`, the default, the shape of
  `initial_value` must be known.
* <b>`caching_device`</b>: Optional device string describing where the Variable
  should be cached for reading.  Defaults to the Variable's device. If not
  `None`, caches on another device.  Typical use is to cache on the device
  where the Ops using the Variable reside, to deduplicate copying through
  `Switch` and other conditional statements.
* <b>`name`</b>: Optional name for the variable. Defaults to `'Variable'` and gets
  uniquified automatically.
* <b>`variable_def`</b>: `VariableDef` protocol buffer. If not `None`, recreates the
  Variable object with its contents, referencing the variable's nodes in
  the graph, which must already exist. The graph is not changed.
  `variable_def` and the other arguments are mutually exclusive.
* <b>`dtype`</b>: If set, initial_value will be converted to the given type. If
  `None`, either the datatype will be kept (if `initial_value` is a
  Tensor), or `convert_to_tensor` will decide.
* <b>`import_scope`</b>: Optional `string`. Name scope to add to the `Variable.` Only
  used when initializing from protocol buffer.
* <b>`constraint`</b>: An optional projection function to be applied to the variable
  after being updated by an `Optimizer` (e.g. used to implement norm
  constraints or value constraints for layer weights). The function must
  take as input the unprojected Tensor representing the value of the
  variable and return the Tensor for the projected value (which must have
  the same shape). Constraints are not safe to use when doing asynchronous
  distributed training.
* <b>`synchronization`</b>: Indicates when a distributed a variable will be
  aggregated. Accepted values are constants defined in the class
  <a href="../tf/VariableSynchronization.md"><code>tf.VariableSynchronization</code></a>. By default the synchronization is set to
  `AUTO` and the current `DistributionStrategy` chooses when to
  synchronize.
* <b>`aggregation`</b>: Indicates how a distributed variable will be aggregated.
  Accepted values are constants defined in the class
  <a href="../tf/VariableAggregation.md"><code>tf.VariableAggregation</code></a>.
* <b>`shape`</b>: (optional) The shape of this variable. If None, the shape of
  `initial_value` will be used. When setting this argument to
  <a href="../tf/TensorShape.md"><code>tf.TensorShape(None)</code></a> (representing an unspecified shape), the variable
  can be assigned with values of different shapes.


#### Raises:


* <b>`ValueError`</b>: If both `variable_def` and initial_value are specified.
* <b>`ValueError`</b>: If the initial value is not specified, or does not have a
  shape and `validate_shape` is `True`.



## Child Classes
[`class SaveSliceInfo`](../tf/Variable/SaveSliceInfo.md)

## Properties

<h3 id="aggregation"><code>aggregation</code></h3>




<h3 id="constraint"><code>constraint</code></h3>

Returns the constraint function associated with this variable.


#### Returns:

The constraint function that was passed to the variable constructor.
Can be `None` if no constraint was passed.


<h3 id="device"><code>device</code></h3>

The device of this variable.


<h3 id="dtype"><code>dtype</code></h3>

The `DType` of this variable.


<h3 id="graph"><code>graph</code></h3>

The `Graph` of this variable.


<h3 id="initial_value"><code>initial_value</code></h3>

Returns the Tensor used as the initial value for the variable.

Note that this is different from `initialized_value()` which runs
the op that initializes the variable before returning its value.
This method returns the tensor that is used by the op that initializes
the variable.

#### Returns:

A `Tensor`.


<h3 id="initializer"><code>initializer</code></h3>

The initializer operation for this variable.


<h3 id="name"><code>name</code></h3>

The name of this variable.


<h3 id="op"><code>op</code></h3>

The `Operation` of this variable.


<h3 id="shape"><code>shape</code></h3>

The `TensorShape` of this variable.


#### Returns:

A `TensorShape`.


<h3 id="synchronization"><code>synchronization</code></h3>




<h3 id="trainable"><code>trainable</code></h3>






## Methods

<h3 id="__abs__"><code>__abs__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/math_ops.py">View source</a>

``` python
__abs__(
    x,
    name=None
)
```

Computes the absolute value of a tensor.

Given a tensor of integer or floating-point values, this operation returns a
tensor of the same type, where each element contains the absolute value of the
corresponding element in the input.

Given a tensor `x` of complex numbers, this operation returns a tensor of type
`float32` or `float64` that is the absolute value of each element in `x`. For
a complex number \\(a + bj\\), its absolute value is computed as \\(\sqrt{a^2
+ b^2}\\).  For example:

```
>>> x = tf.constant([[-2.25 + 4.75j], [-3.25 + 5.75j]])
>>> tf.abs(x)
<tf.Tensor: shape=(2, 1), dtype=float64, numpy=
array([[5.25594901],
       [6.60492241]])>
```

#### Args:


* <b>`x`</b>: A `Tensor` or `SparseTensor` of type `float16`, `float32`, `float64`,
  `int32`, `int64`, `complex64` or `complex128`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` or `SparseTensor` of the same size, type and sparsity as `x`,
  with absolute values. Note, for `complex64` or `complex128` input, the
  returned `Tensor` will be of type `float32` or `float64`, respectively.


<h3 id="__add__"><code>__add__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
__add__(
    a,
    *args,
    **kwargs
)
```

Dispatches to add for strings and add_v2 for all other types.


<h3 id="__and__"><code>__and__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
__and__(
    a,
    *args,
    **kwargs
)
```

Returns the truth value of x AND y element-wise.

*NOTE*: `LogicalAnd` supports broadcasting. More about broadcasting
[here](http://docs.scipy.org/doc/numpy/user/basics.broadcasting.html)

#### Args:


* <b>`x`</b>: A `Tensor` of type `bool`.
* <b>`y`</b>: A `Tensor` of type `bool`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `bool`.


<h3 id="__div__"><code>__div__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
__div__(
    a,
    *args,
    **kwargs
)
```

Divide two values using Python 2 semantics.

Used for Tensor.__div__.

#### Args:


* <b>`x`</b>: `Tensor` numerator of real numeric type.
* <b>`y`</b>: `Tensor` denominator of real numeric type.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

`x / y` returns the quotient of x and y.


<h3 id="__eq__"><code>__eq__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
__eq__(other)
```

Compares two variables element-wise for equality.


<h3 id="__floordiv__"><code>__floordiv__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
__floordiv__(
    a,
    *args,
    **kwargs
)
```

Divides `x / y` elementwise, rounding toward the most negative integer.

The same as <a href="../tf/RaggedTensor.md#__div__"><code>tf.compat.v1.div(x,y)</code></a> for integers, but uses
`tf.floor(tf.compat.v1.div(x,y))` for
floating point arguments so that the result is always an integer (though
possibly an integer represented as floating point).  This op is generated by
`x // y` floor division in Python 3 and in Python 2.7 with
`from __future__ import division`.

`x` and `y` must have the same type, and the result will have the same type
as well.

#### Args:


* <b>`x`</b>: `Tensor` numerator of real numeric type.
* <b>`y`</b>: `Tensor` denominator of real numeric type.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

`x / y` rounded down.



#### Raises:


* <b>`TypeError`</b>: If the inputs are complex.

<h3 id="__ge__"><code>__ge__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
__ge__(
    a,
    *args,
    **kwargs
)
```

Returns the truth value of (x >= y) element-wise.

*NOTE*: <a href="../tf/math/greater_equal.md"><code>math.greater_equal</code></a> supports broadcasting. More about broadcasting
[here](http://docs.scipy.org/doc/numpy/user/basics.broadcasting.html)

#### Example:



```python
x = tf.constant([5, 4, 6, 7])
y = tf.constant([5, 2, 5, 10])
tf.math.greater_equal(x, y) ==> [True, True, True, False]

x = tf.constant([5, 4, 6, 7])
y = tf.constant([5])
tf.math.greater_equal(x, y) ==> [True, False, True, True]
```

#### Args:


* <b>`x`</b>: A `Tensor`. Must be one of the following types: `float32`, `float64`, `int32`, `uint8`, `int16`, `int8`, `int64`, `bfloat16`, `uint16`, `half`, `uint32`, `uint64`.
* <b>`y`</b>: A `Tensor`. Must have the same type as `x`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `bool`.


<h3 id="__getitem__"><code>__getitem__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/array_ops.py">View source</a>

``` python
__getitem__(
    var,
    slice_spec
)
```

Creates a slice helper object given a variable.

This allows creating a sub-tensor from part of the current contents
of a variable. See <a href="../tf/Tensor.md#__getitem__"><code>tf.Tensor.__getitem__</code></a> for detailed examples
of slicing.

This function in addition also allows assignment to a sliced range.
This is similar to `__setitem__` functionality in Python. However,
the syntax is different so that the user can capture the assignment
operation for grouping or passing to `sess.run()`.
For example,

```python
import tensorflow as tf
A = tf.Variable([[1,2,3], [4,5,6], [7,8,9]], dtype=tf.float32)
with tf.compat.v1.Session() as sess:
  sess.run(tf.compat.v1.global_variables_initializer())
  print(sess.run(A[:2, :2]))  # => [[1,2], [4,5]]

  op = A[:2,:2].assign(22. * tf.ones((2, 2)))
  print(sess.run(op))  # => [[22, 22, 3], [22, 22, 6], [7,8,9]]
```

Note that assignments currently do not support NumPy broadcasting
semantics.

#### Args:


* <b>`var`</b>: An `ops.Variable` object.
* <b>`slice_spec`</b>: The arguments to <a href="../tf/Tensor.md#__getitem__"><code>Tensor.__getitem__</code></a>.


#### Returns:

The appropriate slice of "tensor", based on "slice_spec".
As an operator. The operator also has a `assign()` method
that can be used to generate an assignment operator.



#### Raises:


* <b>`ValueError`</b>: If a slice range is negative size.
* <b>`TypeError`</b>: TypeError: If the slice indices aren't int, slice,
  ellipsis, tf.newaxis or int32/int64 tensors.

<h3 id="__gt__"><code>__gt__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
__gt__(
    a,
    *args,
    **kwargs
)
```

Returns the truth value of (x > y) element-wise.

*NOTE*: <a href="../tf/math/greater.md"><code>math.greater</code></a> supports broadcasting. More about broadcasting
[here](http://docs.scipy.org/doc/numpy/user/basics.broadcasting.html)

#### Example:



```python
x = tf.constant([5, 4, 6])
y = tf.constant([5, 2, 5])
tf.math.greater(x, y) ==> [False, True, True]

x = tf.constant([5, 4, 6])
y = tf.constant([5])
tf.math.greater(x, y) ==> [False, False, True]
```

#### Args:


* <b>`x`</b>: A `Tensor`. Must be one of the following types: `float32`, `float64`, `int32`, `uint8`, `int16`, `int8`, `int64`, `bfloat16`, `uint16`, `half`, `uint32`, `uint64`.
* <b>`y`</b>: A `Tensor`. Must have the same type as `x`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `bool`.


<h3 id="__invert__"><code>__invert__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
__invert__(
    a,
    *args,
    **kwargs
)
```

Returns the truth value of `NOT x` element-wise.


#### Example:



```
>>> tf.math.logical_not(tf.constant([True, False]))
<tf.Tensor: shape=(2,), dtype=bool, numpy=array([False,  True])>
```

#### Args:


* <b>`x`</b>: A `Tensor` of type `bool`. A `Tensor` of type `bool`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `bool`.


<h3 id="__iter__"><code>__iter__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
__iter__()
```

Dummy method to prevent iteration.

Do not call.

NOTE(mrry): If we register __getitem__ as an overloaded operator,
Python will valiantly attempt to iterate over the variable's Tensor from 0
to infinity.  Declaring this method prevents this unintended behavior.

#### Raises:


* <b>`TypeError`</b>: when invoked.

<h3 id="__le__"><code>__le__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
__le__(
    a,
    *args,
    **kwargs
)
```

Returns the truth value of (x <= y) element-wise.

*NOTE*: <a href="../tf/math/less_equal.md"><code>math.less_equal</code></a> supports broadcasting. More about broadcasting
[here](http://docs.scipy.org/doc/numpy/user/basics.broadcasting.html)

#### Example:



```python
x = tf.constant([5, 4, 6])
y = tf.constant([5])
tf.math.less_equal(x, y) ==> [True, True, False]

x = tf.constant([5, 4, 6])
y = tf.constant([5, 6, 6])
tf.math.less_equal(x, y) ==> [True, True, True]
```

#### Args:


* <b>`x`</b>: A `Tensor`. Must be one of the following types: `float32`, `float64`, `int32`, `uint8`, `int16`, `int8`, `int64`, `bfloat16`, `uint16`, `half`, `uint32`, `uint64`.
* <b>`y`</b>: A `Tensor`. Must have the same type as `x`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `bool`.


<h3 id="__lt__"><code>__lt__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
__lt__(
    a,
    *args,
    **kwargs
)
```

Returns the truth value of (x < y) element-wise.

*NOTE*: <a href="../tf/math/less.md"><code>math.less</code></a> supports broadcasting. More about broadcasting
[here](http://docs.scipy.org/doc/numpy/user/basics.broadcasting.html)

#### Example:



```python
x = tf.constant([5, 4, 6])
y = tf.constant([5])
tf.math.less(x, y) ==> [False, True, False]

x = tf.constant([5, 4, 6])
y = tf.constant([5, 6, 7])
tf.math.less(x, y) ==> [False, True, True]
```

#### Args:


* <b>`x`</b>: A `Tensor`. Must be one of the following types: `float32`, `float64`, `int32`, `uint8`, `int16`, `int8`, `int64`, `bfloat16`, `uint16`, `half`, `uint32`, `uint64`.
* <b>`y`</b>: A `Tensor`. Must have the same type as `x`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `bool`.


<h3 id="__matmul__"><code>__matmul__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
__matmul__(
    a,
    *args,
    **kwargs
)
```

Multiplies matrix `a` by matrix `b`, producing `a` * `b`.

The inputs must, following any transpositions, be tensors of rank >= 2
where the inner 2 dimensions specify valid matrix multiplication dimensions,
and any further outer dimensions specify matching batch size.

Both matrices must be of the same type. The supported types are:
`float16`, `float32`, `float64`, `int32`, `complex64`, `complex128`.

Either matrix can be transposed or adjointed (conjugated and transposed) on
the fly by setting one of the corresponding flag to `True`. These are `False`
by default.

If one or both of the matrices contain a lot of zeros, a more efficient
multiplication algorithm can be used by setting the corresponding
`a_is_sparse` or `b_is_sparse` flag to `True`. These are `False` by default.
This optimization is only available for plain matrices (rank-2 tensors) with
datatypes `bfloat16` or `float32`.

A simple 2-D tensor matrix multiplication:

```
>>> a = tf.constant([1, 2, 3, 4, 5, 6], shape=[2, 3])
>>> a  # 2-D tensor
<tf.Tensor: shape=(2, 3), dtype=int32, numpy=
array([[1, 2, 3],
       [4, 5, 6]], dtype=int32)>
>>> b = tf.constant([7, 8, 9, 10, 11, 12], shape=[3, 2])
>>> b  # 2-D tensor
<tf.Tensor: shape=(3, 2), dtype=int32, numpy=
array([[ 7,  8],
       [ 9, 10],
       [11, 12]], dtype=int32)>
>>> c = tf.matmul(a, b)
>>> c  # `a` * `b`
<tf.Tensor: shape=(2, 2), dtype=int32, numpy=
array([[ 58,  64],
       [139, 154]], dtype=int32)>
```

A batch matrix multiplication with batch shape [2]:

```
>>> a = tf.constant(np.arange(1, 13, dtype=np.int32), shape=[2, 2, 3])
>>> a  # 3-D tensor
<tf.Tensor: shape=(2, 2, 3), dtype=int32, numpy=
array([[[ 1,  2,  3],
        [ 4,  5,  6]],
       [[ 7,  8,  9],
        [10, 11, 12]]], dtype=int32)>
>>> b = tf.constant(np.arange(13, 25, dtype=np.int32), shape=[2, 3, 2])
>>> b  # 3-D tensor
<tf.Tensor: shape=(2, 3, 2), dtype=int32, numpy=
array([[[13, 14],
        [15, 16],
        [17, 18]],
       [[19, 20],
        [21, 22],
        [23, 24]]], dtype=int32)>
>>> c = tf.matmul(a, b)
>>> c  # `a` * `b`
<tf.Tensor: shape=(2, 2, 2), dtype=int32, numpy=
array([[[ 94, 100],
        [229, 244]],
       [[508, 532],
        [697, 730]]], dtype=int32)>
```

Since python >= 3.5 the @ operator is supported
(see [PEP 465](https://www.python.org/dev/peps/pep-0465/)). In TensorFlow,
it simply calls the <a href="../tf/linalg/matmul.md"><code>tf.matmul()</code></a> function, so the following lines are
equivalent:

```
>>> d = a @ b @ [[10], [11]]
>>> d = tf.matmul(tf.matmul(a, b), [[10], [11]])
```

#### Args:


* <b>`a`</b>: <a href="../tf/Tensor.md"><code>tf.Tensor</code></a> of type `float16`, `float32`, `float64`, `int32`,
  `complex64`, `complex128` and rank > 1.
* <b>`b`</b>: <a href="../tf/Tensor.md"><code>tf.Tensor</code></a> with same type and rank as `a`.
* <b>`transpose_a`</b>: If `True`, `a` is transposed before multiplication.
* <b>`transpose_b`</b>: If `True`, `b` is transposed before multiplication.
* <b>`adjoint_a`</b>: If `True`, `a` is conjugated and transposed before
  multiplication.
* <b>`adjoint_b`</b>: If `True`, `b` is conjugated and transposed before
  multiplication.
* <b>`a_is_sparse`</b>: If `True`, `a` is treated as a sparse matrix.
* <b>`b_is_sparse`</b>: If `True`, `b` is treated as a sparse matrix.
* <b>`name`</b>: Name for the operation (optional).


#### Returns:

A <a href="../tf/Tensor.md"><code>tf.Tensor</code></a> of the same type as `a` and `b` where each inner-most matrix
is the product of the corresponding matrices in `a` and `b`, e.g. if all
transpose or adjoint attributes are `False`:

`output[..., i, j] = sum_k (a[..., i, k] * b[..., k, j])`,
for all indices `i`, `j`.


* <b>`Note`</b>: This is matrix product, not element-wise product.



#### Raises:


* <b>`ValueError`</b>: If `transpose_a` and `adjoint_a`, or `transpose_b` and
  `adjoint_b` are both set to `True`.

<h3 id="__mod__"><code>__mod__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
__mod__(
    a,
    *args,
    **kwargs
)
```

Returns element-wise remainder of division. When `x < 0` xor `y < 0` is

true, this follows Python semantics in that the result here is consistent
with a flooring divide. E.g. `floor(x / y) * y + mod(x, y) = x`.

*NOTE*: <a href="../tf/math/floormod.md"><code>math.floormod</code></a> supports broadcasting. More about broadcasting
[here](http://docs.scipy.org/doc/numpy/user/basics.broadcasting.html)

#### Args:


* <b>`x`</b>: A `Tensor`. Must be one of the following types: `int32`, `int64`, `bfloat16`, `half`, `float32`, `float64`.
* <b>`y`</b>: A `Tensor`. Must have the same type as `x`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.


<h3 id="__mul__"><code>__mul__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
__mul__(
    a,
    *args,
    **kwargs
)
```

Dispatches cwise mul for "Dense*Dense" and "Dense*Sparse".


<h3 id="__ne__"><code>__ne__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
__ne__(other)
```

Compares two variables element-wise for equality.


<h3 id="__neg__"><code>__neg__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
__neg__(
    a,
    *args,
    **kwargs
)
```

Computes numerical negative value element-wise.

I.e., \\(y = -x\\).

#### Args:


* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`, `int32`, `int64`, `complex64`, `complex128`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.


<h3 id="__or__"><code>__or__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
__or__(
    a,
    *args,
    **kwargs
)
```

Returns the truth value of x OR y element-wise.

*NOTE*: <a href="../tf/math/logical_or.md"><code>math.logical_or</code></a> supports broadcasting. More about broadcasting
[here](http://docs.scipy.org/doc/numpy/user/basics.broadcasting.html)

#### Args:


* <b>`x`</b>: A `Tensor` of type `bool`.
* <b>`y`</b>: A `Tensor` of type `bool`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `bool`.


<h3 id="__pow__"><code>__pow__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
__pow__(
    a,
    *args,
    **kwargs
)
```

Computes the power of one value to another.

Given a tensor `x` and a tensor `y`, this operation computes \\(x^y\\) for
corresponding elements in `x` and `y`. For example:

```python
x = tf.constant([[2, 2], [3, 3]])
y = tf.constant([[8, 16], [2, 3]])
tf.pow(x, y)  # [[256, 65536], [9, 27]]
```

#### Args:


* <b>`x`</b>: A `Tensor` of type `float16`, `float32`, `float64`, `int32`, `int64`,
  `complex64`, or `complex128`.
* <b>`y`</b>: A `Tensor` of type `float16`, `float32`, `float64`, `int32`, `int64`,
  `complex64`, or `complex128`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`.


<h3 id="__radd__"><code>__radd__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
__radd__(
    a,
    *args,
    **kwargs
)
```

Dispatches to add for strings and add_v2 for all other types.


<h3 id="__rand__"><code>__rand__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
__rand__(
    a,
    *args,
    **kwargs
)
```

Returns the truth value of x AND y element-wise.

*NOTE*: `LogicalAnd` supports broadcasting. More about broadcasting
[here](http://docs.scipy.org/doc/numpy/user/basics.broadcasting.html)

#### Args:


* <b>`x`</b>: A `Tensor` of type `bool`.
* <b>`y`</b>: A `Tensor` of type `bool`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `bool`.


<h3 id="__rdiv__"><code>__rdiv__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
__rdiv__(
    a,
    *args,
    **kwargs
)
```

Divide two values using Python 2 semantics.

Used for Tensor.__div__.

#### Args:


* <b>`x`</b>: `Tensor` numerator of real numeric type.
* <b>`y`</b>: `Tensor` denominator of real numeric type.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

`x / y` returns the quotient of x and y.


<h3 id="__rfloordiv__"><code>__rfloordiv__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
__rfloordiv__(
    a,
    *args,
    **kwargs
)
```

Divides `x / y` elementwise, rounding toward the most negative integer.

The same as <a href="../tf/RaggedTensor.md#__div__"><code>tf.compat.v1.div(x,y)</code></a> for integers, but uses
`tf.floor(tf.compat.v1.div(x,y))` for
floating point arguments so that the result is always an integer (though
possibly an integer represented as floating point).  This op is generated by
`x // y` floor division in Python 3 and in Python 2.7 with
`from __future__ import division`.

`x` and `y` must have the same type, and the result will have the same type
as well.

#### Args:


* <b>`x`</b>: `Tensor` numerator of real numeric type.
* <b>`y`</b>: `Tensor` denominator of real numeric type.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

`x / y` rounded down.



#### Raises:


* <b>`TypeError`</b>: If the inputs are complex.

<h3 id="__rmatmul__"><code>__rmatmul__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
__rmatmul__(
    a,
    *args,
    **kwargs
)
```

Multiplies matrix `a` by matrix `b`, producing `a` * `b`.

The inputs must, following any transpositions, be tensors of rank >= 2
where the inner 2 dimensions specify valid matrix multiplication dimensions,
and any further outer dimensions specify matching batch size.

Both matrices must be of the same type. The supported types are:
`float16`, `float32`, `float64`, `int32`, `complex64`, `complex128`.

Either matrix can be transposed or adjointed (conjugated and transposed) on
the fly by setting one of the corresponding flag to `True`. These are `False`
by default.

If one or both of the matrices contain a lot of zeros, a more efficient
multiplication algorithm can be used by setting the corresponding
`a_is_sparse` or `b_is_sparse` flag to `True`. These are `False` by default.
This optimization is only available for plain matrices (rank-2 tensors) with
datatypes `bfloat16` or `float32`.

A simple 2-D tensor matrix multiplication:

```
>>> a = tf.constant([1, 2, 3, 4, 5, 6], shape=[2, 3])
>>> a  # 2-D tensor
<tf.Tensor: shape=(2, 3), dtype=int32, numpy=
array([[1, 2, 3],
       [4, 5, 6]], dtype=int32)>
>>> b = tf.constant([7, 8, 9, 10, 11, 12], shape=[3, 2])
>>> b  # 2-D tensor
<tf.Tensor: shape=(3, 2), dtype=int32, numpy=
array([[ 7,  8],
       [ 9, 10],
       [11, 12]], dtype=int32)>
>>> c = tf.matmul(a, b)
>>> c  # `a` * `b`
<tf.Tensor: shape=(2, 2), dtype=int32, numpy=
array([[ 58,  64],
       [139, 154]], dtype=int32)>
```

A batch matrix multiplication with batch shape [2]:

```
>>> a = tf.constant(np.arange(1, 13, dtype=np.int32), shape=[2, 2, 3])
>>> a  # 3-D tensor
<tf.Tensor: shape=(2, 2, 3), dtype=int32, numpy=
array([[[ 1,  2,  3],
        [ 4,  5,  6]],
       [[ 7,  8,  9],
        [10, 11, 12]]], dtype=int32)>
>>> b = tf.constant(np.arange(13, 25, dtype=np.int32), shape=[2, 3, 2])
>>> b  # 3-D tensor
<tf.Tensor: shape=(2, 3, 2), dtype=int32, numpy=
array([[[13, 14],
        [15, 16],
        [17, 18]],
       [[19, 20],
        [21, 22],
        [23, 24]]], dtype=int32)>
>>> c = tf.matmul(a, b)
>>> c  # `a` * `b`
<tf.Tensor: shape=(2, 2, 2), dtype=int32, numpy=
array([[[ 94, 100],
        [229, 244]],
       [[508, 532],
        [697, 730]]], dtype=int32)>
```

Since python >= 3.5 the @ operator is supported
(see [PEP 465](https://www.python.org/dev/peps/pep-0465/)). In TensorFlow,
it simply calls the <a href="../tf/linalg/matmul.md"><code>tf.matmul()</code></a> function, so the following lines are
equivalent:

```
>>> d = a @ b @ [[10], [11]]
>>> d = tf.matmul(tf.matmul(a, b), [[10], [11]])
```

#### Args:


* <b>`a`</b>: <a href="../tf/Tensor.md"><code>tf.Tensor</code></a> of type `float16`, `float32`, `float64`, `int32`,
  `complex64`, `complex128` and rank > 1.
* <b>`b`</b>: <a href="../tf/Tensor.md"><code>tf.Tensor</code></a> with same type and rank as `a`.
* <b>`transpose_a`</b>: If `True`, `a` is transposed before multiplication.
* <b>`transpose_b`</b>: If `True`, `b` is transposed before multiplication.
* <b>`adjoint_a`</b>: If `True`, `a` is conjugated and transposed before
  multiplication.
* <b>`adjoint_b`</b>: If `True`, `b` is conjugated and transposed before
  multiplication.
* <b>`a_is_sparse`</b>: If `True`, `a` is treated as a sparse matrix.
* <b>`b_is_sparse`</b>: If `True`, `b` is treated as a sparse matrix.
* <b>`name`</b>: Name for the operation (optional).


#### Returns:

A <a href="../tf/Tensor.md"><code>tf.Tensor</code></a> of the same type as `a` and `b` where each inner-most matrix
is the product of the corresponding matrices in `a` and `b`, e.g. if all
transpose or adjoint attributes are `False`:

`output[..., i, j] = sum_k (a[..., i, k] * b[..., k, j])`,
for all indices `i`, `j`.


* <b>`Note`</b>: This is matrix product, not element-wise product.



#### Raises:


* <b>`ValueError`</b>: If `transpose_a` and `adjoint_a`, or `transpose_b` and
  `adjoint_b` are both set to `True`.

<h3 id="__rmod__"><code>__rmod__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
__rmod__(
    a,
    *args,
    **kwargs
)
```

Returns element-wise remainder of division. When `x < 0` xor `y < 0` is

true, this follows Python semantics in that the result here is consistent
with a flooring divide. E.g. `floor(x / y) * y + mod(x, y) = x`.

*NOTE*: <a href="../tf/math/floormod.md"><code>math.floormod</code></a> supports broadcasting. More about broadcasting
[here](http://docs.scipy.org/doc/numpy/user/basics.broadcasting.html)

#### Args:


* <b>`x`</b>: A `Tensor`. Must be one of the following types: `int32`, `int64`, `bfloat16`, `half`, `float32`, `float64`.
* <b>`y`</b>: A `Tensor`. Must have the same type as `x`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.


<h3 id="__rmul__"><code>__rmul__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
__rmul__(
    a,
    *args,
    **kwargs
)
```

Dispatches cwise mul for "Dense*Dense" and "Dense*Sparse".


<h3 id="__ror__"><code>__ror__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
__ror__(
    a,
    *args,
    **kwargs
)
```

Returns the truth value of x OR y element-wise.

*NOTE*: <a href="../tf/math/logical_or.md"><code>math.logical_or</code></a> supports broadcasting. More about broadcasting
[here](http://docs.scipy.org/doc/numpy/user/basics.broadcasting.html)

#### Args:


* <b>`x`</b>: A `Tensor` of type `bool`.
* <b>`y`</b>: A `Tensor` of type `bool`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `bool`.


<h3 id="__rpow__"><code>__rpow__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
__rpow__(
    a,
    *args,
    **kwargs
)
```

Computes the power of one value to another.

Given a tensor `x` and a tensor `y`, this operation computes \\(x^y\\) for
corresponding elements in `x` and `y`. For example:

```python
x = tf.constant([[2, 2], [3, 3]])
y = tf.constant([[8, 16], [2, 3]])
tf.pow(x, y)  # [[256, 65536], [9, 27]]
```

#### Args:


* <b>`x`</b>: A `Tensor` of type `float16`, `float32`, `float64`, `int32`, `int64`,
  `complex64`, or `complex128`.
* <b>`y`</b>: A `Tensor` of type `float16`, `float32`, `float64`, `int32`, `int64`,
  `complex64`, or `complex128`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`.


<h3 id="__rsub__"><code>__rsub__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
__rsub__(
    a,
    *args,
    **kwargs
)
```

Returns x - y element-wise.

*NOTE*: `Subtract` supports broadcasting. More about broadcasting
[here](http://docs.scipy.org/doc/numpy/user/basics.broadcasting.html)

#### Args:


* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`, `uint8`, `int8`, `uint16`, `int16`, `int32`, `int64`, `complex64`, `complex128`.
* <b>`y`</b>: A `Tensor`. Must have the same type as `x`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.


<h3 id="__rtruediv__"><code>__rtruediv__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
__rtruediv__(
    a,
    *args,
    **kwargs
)
```




<h3 id="__rxor__"><code>__rxor__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
__rxor__(
    a,
    *args,
    **kwargs
)
```

Logical XOR function.

x ^ y = (x | y) & ~(x & y)

The operation works for the following input types:

- Two single elements of type `bool`
- One <a href="../tf/Tensor.md"><code>tf.Tensor</code></a> of type `bool` and one single `bool`, where the result will
  be calculated by applying logical XOR with the single element to each
  element in the larger Tensor.
- Two <a href="../tf/Tensor.md"><code>tf.Tensor</code></a> objects of type `bool` of the same shape. In this case,
  the result will be the element-wise logical XOR of the two input tensors.

#### Usage:



```
>>> a = tf.constant([True])
>>> b = tf.constant([False])
>>> tf.math.logical_xor(a, b)
<tf.Tensor: shape=(1,), dtype=bool, numpy=array([ True])>
```

```
>>> c = tf.constant([True])
>>> x = tf.constant([False, True, True, False])
>>> tf.math.logical_xor(c, x)
<tf.Tensor: shape=(4,), dtype=bool, numpy=array([ True, False, False,  True])>
```

```
>>> y = tf.constant([False, False, True, True])
>>> z = tf.constant([False, True, False, True])
>>> tf.math.logical_xor(y, z)
<tf.Tensor: shape=(4,), dtype=bool, numpy=array([False,  True,  True, False])>
```

#### Args:


* <b>`x`</b>: A <a href="../tf/Tensor.md"><code>tf.Tensor</code></a> type bool.
* <b>`y`</b>: A <a href="../tf/Tensor.md"><code>tf.Tensor</code></a> of type bool.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A <a href="../tf/Tensor.md"><code>tf.Tensor</code></a> of type bool with the same size as that of x or y.


<h3 id="__sub__"><code>__sub__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
__sub__(
    a,
    *args,
    **kwargs
)
```

Returns x - y element-wise.

*NOTE*: `Subtract` supports broadcasting. More about broadcasting
[here](http://docs.scipy.org/doc/numpy/user/basics.broadcasting.html)

#### Args:


* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`, `uint8`, `int8`, `uint16`, `int16`, `int32`, `int64`, `complex64`, `complex128`.
* <b>`y`</b>: A `Tensor`. Must have the same type as `x`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.


<h3 id="__truediv__"><code>__truediv__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
__truediv__(
    a,
    *args,
    **kwargs
)
```




<h3 id="__xor__"><code>__xor__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
__xor__(
    a,
    *args,
    **kwargs
)
```

Logical XOR function.

x ^ y = (x | y) & ~(x & y)

The operation works for the following input types:

- Two single elements of type `bool`
- One <a href="../tf/Tensor.md"><code>tf.Tensor</code></a> of type `bool` and one single `bool`, where the result will
  be calculated by applying logical XOR with the single element to each
  element in the larger Tensor.
- Two <a href="../tf/Tensor.md"><code>tf.Tensor</code></a> objects of type `bool` of the same shape. In this case,
  the result will be the element-wise logical XOR of the two input tensors.

#### Usage:



```
>>> a = tf.constant([True])
>>> b = tf.constant([False])
>>> tf.math.logical_xor(a, b)
<tf.Tensor: shape=(1,), dtype=bool, numpy=array([ True])>
```

```
>>> c = tf.constant([True])
>>> x = tf.constant([False, True, True, False])
>>> tf.math.logical_xor(c, x)
<tf.Tensor: shape=(4,), dtype=bool, numpy=array([ True, False, False,  True])>
```

```
>>> y = tf.constant([False, False, True, True])
>>> z = tf.constant([False, True, False, True])
>>> tf.math.logical_xor(y, z)
<tf.Tensor: shape=(4,), dtype=bool, numpy=array([False,  True,  True, False])>
```

#### Args:


* <b>`x`</b>: A <a href="../tf/Tensor.md"><code>tf.Tensor</code></a> type bool.
* <b>`y`</b>: A <a href="../tf/Tensor.md"><code>tf.Tensor</code></a> of type bool.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A <a href="../tf/Tensor.md"><code>tf.Tensor</code></a> of type bool with the same size as that of x or y.


<h3 id="assign"><code>assign</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
assign(
    value,
    use_locking=False,
    name=None,
    read_value=True
)
```

Assigns a new value to the variable.

This is essentially a shortcut for `assign(self, value)`.

#### Args:


* <b>`value`</b>: A `Tensor`. The new value for this variable.
* <b>`use_locking`</b>: If `True`, use locking during the assignment.
* <b>`name`</b>: The name of the operation to be created
* <b>`read_value`</b>: if True, will return something which evaluates to the new
  value of the variable; if False will return the assign op.


#### Returns:

A `Tensor` that will hold the new value of this variable after
the assignment has completed.


<h3 id="assign_add"><code>assign_add</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
assign_add(
    delta,
    use_locking=False,
    name=None,
    read_value=True
)
```

Adds a value to this variable.

 This is essentially a shortcut for `assign_add(self, delta)`.

#### Args:


* <b>`delta`</b>: A `Tensor`. The value to add to this variable.
* <b>`use_locking`</b>: If `True`, use locking during the operation.
* <b>`name`</b>: The name of the operation to be created
* <b>`read_value`</b>: if True, will return something which evaluates to the new
  value of the variable; if False will return the assign op.


#### Returns:

A `Tensor` that will hold the new value of this variable after
the addition has completed.


<h3 id="assign_sub"><code>assign_sub</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
assign_sub(
    delta,
    use_locking=False,
    name=None,
    read_value=True
)
```

Subtracts a value from this variable.

This is essentially a shortcut for `assign_sub(self, delta)`.

#### Args:


* <b>`delta`</b>: A `Tensor`. The value to subtract from this variable.
* <b>`use_locking`</b>: If `True`, use locking during the operation.
* <b>`name`</b>: The name of the operation to be created
* <b>`read_value`</b>: if True, will return something which evaluates to the new
  value of the variable; if False will return the assign op.


#### Returns:

A `Tensor` that will hold the new value of this variable after
the subtraction has completed.


<h3 id="batch_scatter_update"><code>batch_scatter_update</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
batch_scatter_update(
    sparse_delta,
    use_locking=False,
    name=None
)
```

Assigns <a href="../tf/IndexedSlices.md"><code>tf.IndexedSlices</code></a> to this variable batch-wise.

Analogous to `batch_gather`. This assumes that this variable and the
sparse_delta IndexedSlices have a series of leading dimensions that are the
same for all of them, and the updates are performed on the last dimension of
indices. In other words, the dimensions should be the following:

`num_prefix_dims = sparse_delta.indices.ndims - 1`
`batch_dim = num_prefix_dims + 1`
`sparse_delta.updates.shape = sparse_delta.indices.shape + var.shape[
     batch_dim:]`

where

`sparse_delta.updates.shape[:num_prefix_dims]`
`== sparse_delta.indices.shape[:num_prefix_dims]`
`== var.shape[:num_prefix_dims]`

And the operation performed can be expressed as:

`var[i_1, ..., i_n,
     sparse_delta.indices[i_1, ..., i_n, j]] = sparse_delta.updates[
        i_1, ..., i_n, j]`

When sparse_delta.indices is a 1D tensor, this operation is equivalent to
`scatter_update`.

To avoid this operation one can looping over the first `ndims` of the
variable and using `scatter_update` on the subtensors that result of slicing
the first dimension. This is a valid option for `ndims = 1`, but less
efficient than this implementation.

#### Args:


* <b>`sparse_delta`</b>: <a href="../tf/IndexedSlices.md"><code>tf.IndexedSlices</code></a> to be assigned to this variable.
* <b>`use_locking`</b>: If `True`, use locking during the operation.
* <b>`name`</b>: the name of the operation.


#### Returns:

A `Tensor` that will hold the new value of this variable after
the scattered assignment has completed.



#### Raises:


* <b>`TypeError`</b>: if `sparse_delta` is not an `IndexedSlices`.

<h3 id="count_up_to"><code>count_up_to</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
count_up_to(limit)
```

Increments this variable until it reaches `limit`. (deprecated)

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Prefer Dataset.range instead.

When that Op is run it tries to increment the variable by `1`. If
incrementing the variable would bring it above `limit` then the Op raises
the exception `OutOfRangeError`.

If no error is raised, the Op outputs the value of the variable before
the increment.

This is essentially a shortcut for `count_up_to(self, limit)`.

#### Args:


* <b>`limit`</b>: value at which incrementing the variable raises an error.


#### Returns:

A `Tensor` that will hold the variable value before the increment. If no
other Op modifies this variable, the values produced will all be
distinct.


<h3 id="eval"><code>eval</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
eval(session=None)
```

In a session, computes and returns the value of this variable.

This is not a graph construction method, it does not add ops to the graph.

This convenience method requires a session where the graph
containing this variable has been launched. If no session is
passed, the default session is used.  See <a href="../tf/compat/v1/Session.md"><code>tf.compat.v1.Session</code></a> for more
information on launching a graph and on sessions.

```python
v = tf.Variable([1, 2])
init = tf.compat.v1.global_variables_initializer()

with tf.compat.v1.Session() as sess:
    sess.run(init)
    # Usage passing the session explicitly.
    print(v.eval(sess))
    # Usage with the default session.  The 'with' block
    # above makes 'sess' the default session.
    print(v.eval())
```

#### Args:


* <b>`session`</b>: The session to use to evaluate this variable. If none, the
  default session is used.


#### Returns:

A numpy `ndarray` with a copy of the value of this variable.


<h3 id="experimental_ref"><code>experimental_ref</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
experimental_ref()
```

Returns a hashable reference object to this Variable.

Warning: Experimental API that could be changed or removed.

The primary usecase for this API is to put variables in a set/dictionary.
We can't put variables in a set/dictionary as `variable.__hash__()` is no
longer available starting Tensorflow 2.0.

```python
import tensorflow as tf

x = tf.Variable(5)
y = tf.Variable(10)
z = tf.Variable(10)

# The followings will raise an exception starting 2.0
# TypeError: Variable is unhashable if Variable equality is enabled.
variable_set = {x, y, z}
variable_dict = {x: 'five', y: 'ten'}
```

Instead, we can use `variable.experimental_ref()`.

```python
variable_set = {x.experimental_ref(),
                y.experimental_ref(),
                z.experimental_ref()}

print(x.experimental_ref() in variable_set)
==> True

variable_dict = {x.experimental_ref(): 'five',
                 y.experimental_ref(): 'ten',
                 z.experimental_ref(): 'ten'}

print(variable_dict[y.experimental_ref()])
==> ten
```

Also, the reference object provides `.deref()` function that returns the
original Variable.

```python
x = tf.Variable(5)
print(x.experimental_ref().deref())
==> <tf.Variable 'Variable:0' shape=() dtype=int32, numpy=5>
```

<h3 id="from_proto"><code>from_proto</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
@staticmethod
from_proto(
    variable_def,
    import_scope=None
)
```

Returns a `Variable` object created from `variable_def`.


<h3 id="gather_nd"><code>gather_nd</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
gather_nd(
    indices,
    name=None
)
```

Gather slices from `params` into a Tensor with shape specified by `indices`.

See tf.gather_nd for details.

#### Args:


* <b>`indices`</b>: A `Tensor`. Must be one of the following types: `int32`, `int64`.
  Index tensor.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `params`.


<h3 id="get_shape"><code>get_shape</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
get_shape()
```

Alias of <a href="../tf/Variable.md#shape"><code>Variable.shape</code></a>.


<h3 id="initialized_value"><code>initialized_value</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
initialized_value()
```

Returns the value of the initialized variable. (deprecated)

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Use Variable.read_value. Variables in 2.X are initialized automatically both in eager and graph (inside tf.defun) contexts.

You should use this instead of the variable itself to initialize another
variable with a value that depends on the value of this variable.

```python
# Initialize 'v' with a random tensor.
v = tf.Variable(tf.random.truncated_normal([10, 40]))
# Use `initialized_value` to guarantee that `v` has been
# initialized before its value is used to initialize `w`.
# The random values are picked only once.
w = tf.Variable(v.initialized_value() * 2.0)
```

#### Returns:

A `Tensor` holding the value of this variable after its initializer
has run.


<h3 id="load"><code>load</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
load(
    value,
    session=None
)
```

Load new value into this variable. (deprecated)

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Prefer Variable.assign which has equivalent behavior in 2.X.

Writes new value to variable's memory. Doesn't add ops to the graph.

This convenience method requires a session where the graph
containing this variable has been launched. If no session is
passed, the default session is used.  See <a href="../tf/compat/v1/Session.md"><code>tf.compat.v1.Session</code></a> for more
information on launching a graph and on sessions.

```python
v = tf.Variable([1, 2])
init = tf.compat.v1.global_variables_initializer()

with tf.compat.v1.Session() as sess:
    sess.run(init)
    # Usage passing the session explicitly.
    v.load([2, 3], sess)
    print(v.eval(sess)) # prints [2 3]
    # Usage with the default session.  The 'with' block
    # above makes 'sess' the default session.
    v.load([3, 4], sess)
    print(v.eval()) # prints [3 4]
```

#### Args:


* <b>`value`</b>: New variable value
* <b>`session`</b>: The session to use to evaluate this variable. If none, the
  default session is used.


#### Raises:


* <b>`ValueError`</b>: Session is not passed and no default session

<h3 id="read_value"><code>read_value</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
read_value()
```

Returns the value of this variable, read in the current context.

Can be different from value() if it's on another device, with control
dependencies, etc.

#### Returns:

A `Tensor` containing the value of the variable.


<h3 id="scatter_add"><code>scatter_add</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
scatter_add(
    sparse_delta,
    use_locking=False,
    name=None
)
```

Adds <a href="../tf/IndexedSlices.md"><code>tf.IndexedSlices</code></a> to this variable.


#### Args:


* <b>`sparse_delta`</b>: <a href="../tf/IndexedSlices.md"><code>tf.IndexedSlices</code></a> to be added to this variable.
* <b>`use_locking`</b>: If `True`, use locking during the operation.
* <b>`name`</b>: the name of the operation.


#### Returns:

A `Tensor` that will hold the new value of this variable after
the scattered addition has completed.



#### Raises:


* <b>`TypeError`</b>: if `sparse_delta` is not an `IndexedSlices`.

<h3 id="scatter_div"><code>scatter_div</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
scatter_div(
    sparse_delta,
    use_locking=False,
    name=None
)
```

Divide this variable by <a href="../tf/IndexedSlices.md"><code>tf.IndexedSlices</code></a>.


#### Args:


* <b>`sparse_delta`</b>: <a href="../tf/IndexedSlices.md"><code>tf.IndexedSlices</code></a> to divide this variable by.
* <b>`use_locking`</b>: If `True`, use locking during the operation.
* <b>`name`</b>: the name of the operation.


#### Returns:

A `Tensor` that will hold the new value of this variable after
the scattered division has completed.



#### Raises:


* <b>`TypeError`</b>: if `sparse_delta` is not an `IndexedSlices`.

<h3 id="scatter_max"><code>scatter_max</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
scatter_max(
    sparse_delta,
    use_locking=False,
    name=None
)
```

Updates this variable with the max of <a href="../tf/IndexedSlices.md"><code>tf.IndexedSlices</code></a> and itself.


#### Args:


* <b>`sparse_delta`</b>: <a href="../tf/IndexedSlices.md"><code>tf.IndexedSlices</code></a> to use as an argument of max with this
  variable.
* <b>`use_locking`</b>: If `True`, use locking during the operation.
* <b>`name`</b>: the name of the operation.


#### Returns:

A `Tensor` that will hold the new value of this variable after
the scattered maximization has completed.



#### Raises:


* <b>`TypeError`</b>: if `sparse_delta` is not an `IndexedSlices`.

<h3 id="scatter_min"><code>scatter_min</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
scatter_min(
    sparse_delta,
    use_locking=False,
    name=None
)
```

Updates this variable with the min of <a href="../tf/IndexedSlices.md"><code>tf.IndexedSlices</code></a> and itself.


#### Args:


* <b>`sparse_delta`</b>: <a href="../tf/IndexedSlices.md"><code>tf.IndexedSlices</code></a> to use as an argument of min with this
  variable.
* <b>`use_locking`</b>: If `True`, use locking during the operation.
* <b>`name`</b>: the name of the operation.


#### Returns:

A `Tensor` that will hold the new value of this variable after
the scattered minimization has completed.



#### Raises:


* <b>`TypeError`</b>: if `sparse_delta` is not an `IndexedSlices`.

<h3 id="scatter_mul"><code>scatter_mul</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
scatter_mul(
    sparse_delta,
    use_locking=False,
    name=None
)
```

Multiply this variable by <a href="../tf/IndexedSlices.md"><code>tf.IndexedSlices</code></a>.


#### Args:


* <b>`sparse_delta`</b>: <a href="../tf/IndexedSlices.md"><code>tf.IndexedSlices</code></a> to multiply this variable by.
* <b>`use_locking`</b>: If `True`, use locking during the operation.
* <b>`name`</b>: the name of the operation.


#### Returns:

A `Tensor` that will hold the new value of this variable after
the scattered multiplication has completed.



#### Raises:


* <b>`TypeError`</b>: if `sparse_delta` is not an `IndexedSlices`.

<h3 id="scatter_nd_add"><code>scatter_nd_add</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
scatter_nd_add(
    indices,
    updates,
    name=None
)
```

Applies sparse addition to individual values or slices in a Variable.

The Variable has rank `P` and `indices` is a `Tensor` of rank `Q`.

`indices` must be integer tensor, containing indices into self.
It must be shape `[d_0, ..., d_{Q-2}, K]` where `0 < K <= P`.

The innermost dimension of `indices` (with length `K`) corresponds to
indices into elements (if `K = P`) or slices (if `K < P`) along the `K`th
dimension of self.

`updates` is `Tensor` of rank `Q-1+P-K` with shape:

```
[d_0, ..., d_{Q-2}, self.shape[K], ..., self.shape[P-1]].
```

For example, say we want to add 4 scattered elements to a rank-1 tensor to
8 elements. In Python, that update would look like this:

```python
    v = tf.Variable([1, 2, 3, 4, 5, 6, 7, 8])
    indices = tf.constant([[4], [3], [1] ,[7]])
    updates = tf.constant([9, 10, 11, 12])
    add = v.scatter_nd_add(indices, updates)
    with tf.compat.v1.Session() as sess:
      print sess.run(add)
```

The resulting update to v would look like this:

    [1, 13, 3, 14, 14, 6, 7, 20]

See <a href="../tf/scatter_nd.md"><code>tf.scatter_nd</code></a> for more details about how to make updates to
slices.

#### Args:


* <b>`indices`</b>: The indices to be used in the operation.
* <b>`updates`</b>: The values to be used in the operation.
* <b>`name`</b>: the name of the operation.


#### Returns:

A `Tensor` that will hold the new value of this variable after
the scattered addition has completed.


<h3 id="scatter_nd_sub"><code>scatter_nd_sub</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
scatter_nd_sub(
    indices,
    updates,
    name=None
)
```

Applies sparse subtraction to individual values or slices in a Variable.

Assuming the variable has rank `P` and `indices` is a `Tensor` of rank `Q`.

`indices` must be integer tensor, containing indices into self.
It must be shape `[d_0, ..., d_{Q-2}, K]` where `0 < K <= P`.

The innermost dimension of `indices` (with length `K`) corresponds to
indices into elements (if `K = P`) or slices (if `K < P`) along the `K`th
dimension of self.

`updates` is `Tensor` of rank `Q-1+P-K` with shape:

```
[d_0, ..., d_{Q-2}, self.shape[K], ..., self.shape[P-1]].
```

For example, say we want to add 4 scattered elements to a rank-1 tensor to
8 elements. In Python, that update would look like this:

```python
    v = tf.Variable([1, 2, 3, 4, 5, 6, 7, 8])
    indices = tf.constant([[4], [3], [1] ,[7]])
    updates = tf.constant([9, 10, 11, 12])
    op = v.scatter_nd_sub(indices, updates)
    with tf.compat.v1.Session() as sess:
      print sess.run(op)
```

The resulting update to v would look like this:

    [1, -9, 3, -6, -6, 6, 7, -4]

See <a href="../tf/scatter_nd.md"><code>tf.scatter_nd</code></a> for more details about how to make updates to
slices.

#### Args:


* <b>`indices`</b>: The indices to be used in the operation.
* <b>`updates`</b>: The values to be used in the operation.
* <b>`name`</b>: the name of the operation.


#### Returns:

A `Tensor` that will hold the new value of this variable after
the scattered subtraction has completed.


<h3 id="scatter_nd_update"><code>scatter_nd_update</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
scatter_nd_update(
    indices,
    updates,
    name=None
)
```

Applies sparse assignment to individual values or slices in a Variable.

The Variable has rank `P` and `indices` is a `Tensor` of rank `Q`.

`indices` must be integer tensor, containing indices into self.
It must be shape `[d_0, ..., d_{Q-2}, K]` where `0 < K <= P`.

The innermost dimension of `indices` (with length `K`) corresponds to
indices into elements (if `K = P`) or slices (if `K < P`) along the `K`th
dimension of self.

`updates` is `Tensor` of rank `Q-1+P-K` with shape:

```
[d_0, ..., d_{Q-2}, self.shape[K], ..., self.shape[P-1]].
```

For example, say we want to add 4 scattered elements to a rank-1 tensor to
8 elements. In Python, that update would look like this:

```python
    v = tf.Variable([1, 2, 3, 4, 5, 6, 7, 8])
    indices = tf.constant([[4], [3], [1] ,[7]])
    updates = tf.constant([9, 10, 11, 12])
    op = v.scatter_nd_assign(indices, updates)
    with tf.compat.v1.Session() as sess:
      print sess.run(op)
```

The resulting update to v would look like this:

    [1, 11, 3, 10, 9, 6, 7, 12]

See <a href="../tf/scatter_nd.md"><code>tf.scatter_nd</code></a> for more details about how to make updates to
slices.

#### Args:


* <b>`indices`</b>: The indices to be used in the operation.
* <b>`updates`</b>: The values to be used in the operation.
* <b>`name`</b>: the name of the operation.


#### Returns:

A `Tensor` that will hold the new value of this variable after
the scattered assignment has completed.


<h3 id="scatter_sub"><code>scatter_sub</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
scatter_sub(
    sparse_delta,
    use_locking=False,
    name=None
)
```

Subtracts <a href="../tf/IndexedSlices.md"><code>tf.IndexedSlices</code></a> from this variable.


#### Args:


* <b>`sparse_delta`</b>: <a href="../tf/IndexedSlices.md"><code>tf.IndexedSlices</code></a> to be subtracted from this variable.
* <b>`use_locking`</b>: If `True`, use locking during the operation.
* <b>`name`</b>: the name of the operation.


#### Returns:

A `Tensor` that will hold the new value of this variable after
the scattered subtraction has completed.



#### Raises:


* <b>`TypeError`</b>: if `sparse_delta` is not an `IndexedSlices`.

<h3 id="scatter_update"><code>scatter_update</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
scatter_update(
    sparse_delta,
    use_locking=False,
    name=None
)
```

Assigns <a href="../tf/IndexedSlices.md"><code>tf.IndexedSlices</code></a> to this variable.


#### Args:


* <b>`sparse_delta`</b>: <a href="../tf/IndexedSlices.md"><code>tf.IndexedSlices</code></a> to be assigned to this variable.
* <b>`use_locking`</b>: If `True`, use locking during the operation.
* <b>`name`</b>: the name of the operation.


#### Returns:

A `Tensor` that will hold the new value of this variable after
the scattered assignment has completed.



#### Raises:


* <b>`TypeError`</b>: if `sparse_delta` is not an `IndexedSlices`.

<h3 id="set_shape"><code>set_shape</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
set_shape(shape)
```

Overrides the shape for this variable.


#### Args:


* <b>`shape`</b>: the `TensorShape` representing the overridden shape.

<h3 id="sparse_read"><code>sparse_read</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
sparse_read(
    indices,
    name=None
)
```

Gather slices from params axis axis according to indices.

This function supports a subset of tf.gather, see tf.gather for details on
usage.

#### Args:


* <b>`indices`</b>: The index `Tensor`.  Must be one of the following types: `int32`,
  `int64`. Must be in range `[0, params.shape[axis])`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `params`.


<h3 id="to_proto"><code>to_proto</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
to_proto(export_scope=None)
```

Converts a `Variable` to a `VariableDef` protocol buffer.


#### Args:


* <b>`export_scope`</b>: Optional `string`. Name scope to remove.


#### Returns:

A `VariableDef` protocol buffer, or `None` if the `Variable` is not
in the specified name scope.


<h3 id="value"><code>value</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>

``` python
value()
```

Returns the last snapshot of this variable.

You usually do not need to call this method as all ops that need the value
of the variable call it automatically through a `convert_to_tensor()` call.

Returns a `Tensor` which holds the value of the variable.  You can not
assign a new value to this tensor as it is not a reference to the variable.

To avoid copies, if the consumer of the returned value is on the same device
as the variable, this actually returns the live value of the variable, not
a copy.  Updates to the variable are seen by the consumer.  If the consumer
is on a different device it will get a copy of the variable.

#### Returns:

A `Tensor` containing the value of the variable.






## Compat aliases

* `tf.compat.v2.Variable`
