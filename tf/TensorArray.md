<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.TensorArray" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="dtype"/>
<meta itemprop="property" content="dynamic_size"/>
<meta itemprop="property" content="element_shape"/>
<meta itemprop="property" content="flow"/>
<meta itemprop="property" content="handle"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="close"/>
<meta itemprop="property" content="concat"/>
<meta itemprop="property" content="gather"/>
<meta itemprop="property" content="grad"/>
<meta itemprop="property" content="identity"/>
<meta itemprop="property" content="read"/>
<meta itemprop="property" content="scatter"/>
<meta itemprop="property" content="size"/>
<meta itemprop="property" content="split"/>
<meta itemprop="property" content="stack"/>
<meta itemprop="property" content="unstack"/>
<meta itemprop="property" content="write"/>
</div>

# tf.TensorArray

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/tensor_array_ops.py">View source</a>



## Class `TensorArray`

Class wrapping dynamic-sized, per-time-step, write-once Tensor arrays.



<!-- Placeholder for "Used in" -->

This class is meant to be used with dynamic iteration primitives such as
`while_loop` and `map_fn`.  It supports gradient back-propagation via special
"flow" control flow dependencies.

Example 1: plain reading and writing.
>>> ta = tf.TensorArray(tf.float32, size=0, dynamic_size=True, clear_after_read=False)
>>> ta = ta.write(0, 10)
>>> ta = ta.write(1, 20)
>>> ta = ta.write(2, 30)
>>>
>>> ta.read(0)
<tf.Tensor: shape=(), dtype=float32, numpy=10.0>
>>> ta.read(1)
<tf.Tensor: shape=(), dtype=float32, numpy=20.0>
>>> ta.read(2)
<tf.Tensor: shape=(), dtype=float32, numpy=30.0>
>>> ta.stack()
<tf.Tensor: shape=(3,), dtype=float32, numpy=array([10., 20., 30.],
dtype=float32)>

Example 2: Fibonacci sequence algorithm that writes in a loop then returns.
>>> @tf.function
... def fibonacci(n):
...   ta = tf.TensorArray(tf.float32, size=0, dynamic_size=True)
...   ta = ta.unstack([0., 1.])
...
...   for i in range(2, n):
...     ta = ta.write(i, ta.read(i - 1) + ta.read(i - 2))
...
...   return ta.stack()
>>>
>>> fibonacci(7)
<tf.Tensor: shape=(7,), dtype=float32,
numpy=array([0., 1., 1., 2., 3., 5., 8.], dtype=float32)>

Example 3: A simple loop interacting with a tf.Variable.
>>> v = tf.Variable(1)
>>>
>>> @tf.function
... def f(x):
...   ta = tf.TensorArray(tf.int32, size=0, dynamic_size=True)
...
...   for i in tf.range(x):
...     v.assign_add(i)
...     ta = ta.write(i, v)
...
...   return ta.stack()
>>>
>>> f(5)
<tf.Tensor: shape=(5,), dtype=int32, numpy=array([ 1,  2,  4,  7, 11],
dtype=int32)>

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/ops/tensor_array_ops.py">View source</a>

``` python
__init__(
    dtype,
    size=None,
    dynamic_size=None,
    clear_after_read=None,
    tensor_array_name=None,
    handle=None,
    flow=None,
    infer_shape=True,
    element_shape=None,
    colocate_with_first_write_call=True,
    name=None
)
```

Construct a new TensorArray or wrap an existing TensorArray handle.

A note about the parameter `name`:

The name of the `TensorArray` (even if passed in) is uniquified: each time
a new `TensorArray` is created at runtime it is assigned its own name for
the duration of the run.  This avoids name collisions if a `TensorArray`
is created within a `while_loop`.

#### Args:


* <b>`dtype`</b>: (required) data type of the TensorArray.
* <b>`size`</b>: (optional) int32 scalar `Tensor`: the size of the TensorArray.
  Required if handle is not provided.
* <b>`dynamic_size`</b>: (optional) Python bool: If true, writes to the TensorArray
  can grow the TensorArray past its initial size.  Default: False.
* <b>`clear_after_read`</b>: Boolean (optional, default: True).  If True, clear
  TensorArray values after reading them.  This disables read-many
  semantics, but allows early release of memory.
* <b>`tensor_array_name`</b>: (optional) Python string: the name of the TensorArray.
  This is used when creating the TensorArray handle.  If this value is
  set, handle should be None.
* <b>`handle`</b>: (optional) A `Tensor` handle to an existing TensorArray.  If this
  is set, tensor_array_name should be None. Only supported in graph mode.
* <b>`flow`</b>: (optional) A float `Tensor` scalar coming from an existing
  <a href="../tf/TensorArray.md#flow"><code>TensorArray.flow</code></a>. Only supported in graph mode.
* <b>`infer_shape`</b>: (optional, default: True) If True, shape inference
  is enabled.  In this case, all elements must have the same shape.
* <b>`element_shape`</b>: (optional, default: None) A `TensorShape` object specifying
  the shape constraints of each of the elements of the TensorArray.
  Need not be fully defined.
* <b>`colocate_with_first_write_call`</b>: If `True`, the TensorArray will be
  colocated on the same device as the Tensor used on its first write
  (write operations include `write`, `unstack`, and `split`).  If `False`,
  the TensorArray will be placed on the device determined by the
  device context available during its initialization.
* <b>`name`</b>: A name for the operation (optional).


#### Raises:


* <b>`ValueError`</b>: if both handle and tensor_array_name are provided.
* <b>`TypeError`</b>: if handle is provided but is not a Tensor.



## Properties

<h3 id="dtype"><code>dtype</code></h3>

The data type of this TensorArray.


<h3 id="dynamic_size"><code>dynamic_size</code></h3>

Python bool; if `True` the TensorArray can grow dynamically.


<h3 id="element_shape"><code>element_shape</code></h3>

The <a href="../tf/TensorShape.md"><code>tf.TensorShape</code></a> of elements in this TensorArray.


<h3 id="flow"><code>flow</code></h3>

The flow `Tensor` forcing ops leading to this TensorArray state.


<h3 id="handle"><code>handle</code></h3>

The reference to the TensorArray.




## Methods

<h3 id="close"><code>close</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/tensor_array_ops.py">View source</a>

``` python
close(name=None)
```

Close the current TensorArray.

**NOTE** The output of this function should be used.  If it is not, a warning will be logged or an error may be raised.  To mark the output as used, call its .mark_used() method.

<h3 id="concat"><code>concat</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/tensor_array_ops.py">View source</a>

``` python
concat(name=None)
```

Return the values in the TensorArray as a concatenated `Tensor`.

All of the values must have been written, their ranks must match, and
and their shapes must all match for all dimensions except the first.

#### Args:


* <b>`name`</b>: A name for the operation (optional).


#### Returns:

All the tensors in the TensorArray concatenated into one tensor.


<h3 id="gather"><code>gather</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/tensor_array_ops.py">View source</a>

``` python
gather(
    indices,
    name=None
)
```

Return selected values in the TensorArray as a packed `Tensor`.

All of selected values must have been written and their shapes
must all match.

#### Args:


* <b>`indices`</b>: A `1-D` `Tensor` taking values in `[0, max_value)`.  If
  the `TensorArray` is not dynamic, `max_value=size()`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

The tensors in the `TensorArray` selected by `indices`, packed into one
tensor.


<h3 id="grad"><code>grad</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/tensor_array_ops.py">View source</a>

``` python
grad(
    source,
    flow=None,
    name=None
)
```




<h3 id="identity"><code>identity</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/tensor_array_ops.py">View source</a>

``` python
identity()
```

Returns a TensorArray with the same content and properties.


#### Returns:

A new TensorArray object with flow that ensures the control dependencies
from the contexts will become control dependencies for writes, reads, etc.
Use this object all for subsequent operations.


<h3 id="read"><code>read</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/tensor_array_ops.py">View source</a>

``` python
read(
    index,
    name=None
)
```

Read the value at location `index` in the TensorArray.


#### Args:


* <b>`index`</b>: 0-D.  int32 tensor with the index to read from.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

The tensor at index `index`.


<h3 id="scatter"><code>scatter</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/tensor_array_ops.py">View source</a>

``` python
scatter(
    indices,
    value,
    name=None
)
```

Scatter the values of a `Tensor` in specific indices of a `TensorArray`.

  Args:
    indices: A `1-D` `Tensor` taking values in `[0, max_value)`.  If
      the `TensorArray` is not dynamic, `max_value=size()`.
    value: (N+1)-D.  Tensor of type `dtype`.  The Tensor to unpack.
    name: A name for the operation (optional).

  Returns:
    A new TensorArray object with flow that ensures the scatter occurs.
    Use this object all for subsequent operations.

  Raises:
    ValueError: if the shape inference fails.
  

**NOTE** The output of this function should be used.  If it is not, a warning will be logged or an error may be raised.  To mark the output as used, call its .mark_used() method.

<h3 id="size"><code>size</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/tensor_array_ops.py">View source</a>

``` python
size(name=None)
```

Return the size of the TensorArray.


<h3 id="split"><code>split</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/tensor_array_ops.py">View source</a>

``` python
split(
    value,
    lengths,
    name=None
)
```

Split the values of a `Tensor` into the TensorArray.

  Args:
    value: (N+1)-D.  Tensor of type `dtype`.  The Tensor to split.
    lengths: 1-D.  int32 vector with the lengths to use when splitting
      `value` along its first dimension.
    name: A name for the operation (optional).

  Returns:
    A new TensorArray object with flow that ensures the split occurs.
    Use this object all for subsequent operations.

  Raises:
    ValueError: if the shape inference fails.
  

**NOTE** The output of this function should be used.  If it is not, a warning will be logged or an error may be raised.  To mark the output as used, call its .mark_used() method.

<h3 id="stack"><code>stack</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/tensor_array_ops.py">View source</a>

``` python
stack(name=None)
```

Return the values in the TensorArray as a stacked `Tensor`.

All of the values must have been written and their shapes must all match.
If input shapes have rank-`R`, then output shape will have rank-`(R+1)`.

#### Args:


* <b>`name`</b>: A name for the operation (optional).


#### Returns:

All the tensors in the TensorArray stacked into one tensor.


<h3 id="unstack"><code>unstack</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/tensor_array_ops.py">View source</a>

``` python
unstack(
    value,
    name=None
)
```

Unstack the values of a `Tensor` in the TensorArray.

  If input value shapes have rank-`R`, then the output TensorArray will
  contain elements whose shapes are rank-`(R-1)`.

  Args:
    value: (N+1)-D.  Tensor of type `dtype`.  The Tensor to unstack.
    name: A name for the operation (optional).

  Returns:
    A new TensorArray object with flow that ensures the unstack occurs.
    Use this object all for subsequent operations.

  Raises:
    ValueError: if the shape inference fails.
  

**NOTE** The output of this function should be used.  If it is not, a warning will be logged or an error may be raised.  To mark the output as used, call its .mark_used() method.

<h3 id="write"><code>write</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/tensor_array_ops.py">View source</a>

``` python
write(
    index,
    value,
    name=None
)
```

Write `value` into index `index` of the TensorArray.

  Args:
    index: 0-D.  int32 scalar with the index to write to.
    value: N-D.  Tensor of type `dtype`.  The Tensor to write to this index.
    name: A name for the operation (optional).

  Returns:
    A new TensorArray object with flow that ensures the write occurs.
    Use this object all for subsequent operations.

  Raises:
    ValueError: if there are more writers than specified.
  

**NOTE** The output of this function should be used.  If it is not, a warning will be logged or an error may be raised.  To mark the output as used, call its .mark_used() method.





## Compat aliases

* `tf.compat.v1.TensorArray`
* `tf.compat.v2.TensorArray`

