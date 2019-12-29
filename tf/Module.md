<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.Module" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="name"/>
<meta itemprop="property" content="name_scope"/>
<meta itemprop="property" content="submodules"/>
<meta itemprop="property" content="trainable_variables"/>
<meta itemprop="property" content="variables"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="with_name_scope"/>
</div>

# tf.Module

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/module/module.py">View source</a>



## Class `Module`

Base neural network module class.



<!-- Placeholder for "Used in" -->

A module is a named container for <a href="../tf/Variable.md"><code>tf.Variable</code></a>s, other <a href="../tf/Module.md"><code>tf.Module</code></a>s and
functions which apply to user input. For example a dense layer in a neural
network might be implemented as a <a href="../tf/Module.md"><code>tf.Module</code></a>:

 ```
 >>> class Dense(tf.Module):
 ...   def __init__(self, in_features, out_features, name=None):
 ...     super(Dense, self).__init__(name=name)
 ...     self.w = tf.Variable(
 ...       tf.random.normal([in_features, out_features]), name='w')
 ...     self.b = tf.Variable(tf.zeros([out_features]), name='b')
 ...   def __call__(self, x):
 ...     y = tf.matmul(x, self.w) + self.b
 ...     return tf.nn.relu(y)
 ```

You can use the Dense layer as you would expect:

```
>>> d = Dense(in_features=3, out_features=2)
>>> d(tf.ones([1, 3]))
<tf.Tensor: shape=(1, 2), dtype=float32, numpy=..., dtype=float32)>
```


By subclassing <a href="../tf/Module.md"><code>tf.Module</code></a> instead of `object` any <a href="../tf/Variable.md"><code>tf.Variable</code></a> or
<a href="../tf/Module.md"><code>tf.Module</code></a> instances assigned to object properties can be collected using
the `variables`, `trainable_variables` or `submodules` property:

```
>>> d.variables
    (<tf.Variable 'b:0' shape=(2,) dtype=float32, numpy=...,
    dtype=float32)>,
    <tf.Variable 'w:0' shape=(3, 2) dtype=float32, numpy=..., dtype=float32)>)
```


Subclasses of <a href="../tf/Module.md"><code>tf.Module</code></a> can also take advantage of the `_flatten` method
which can be used to implement tracking of any other types.

All <a href="../tf/Module.md"><code>tf.Module</code></a> classes have an associated <a href="../tf/name_scope.md"><code>tf.name_scope</code></a> which can be used
to group operations in TensorBoard and create hierarchies for variable names
which can help with debugging. We suggest using the name scope when creating
nested submodules/parameters or for forward methods whose graph you might want
to inspect in TensorBoard. You can enter the name scope explicitly using
`with self.name_scope:` or you can annotate methods (apart from `__init__`)
with `@tf.Module.with_name_scope`.

```python
class MLP(tf.Module):
  def __init__(self, input_size, sizes, name=None):
    super(MLP, self).__init__(name=name)
    self.layers = []
    with self.name_scope:
      for size in sizes:
        self.layers.append(Dense(input_size=input_size, output_size=size))
        input_size = size

  @tf.Module.with_name_scope
  def __call__(self, x):
    for layer in self.layers:
      x = layer(x)
    return x
```

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/module/module.py">View source</a>

``` python
__init__(name=None)
```

Initialize self.  See help(type(self)) for accurate signature.




## Properties

<h3 id="name"><code>name</code></h3>

Returns the name of this module as passed or determined in the ctor.

NOTE: This is not the same as the `self.name_scope.name` which includes
parent module names.

<h3 id="name_scope"><code>name_scope</code></h3>

Returns a <a href="../tf/name_scope.md"><code>tf.name_scope</code></a> instance for this class.


<h3 id="submodules"><code>submodules</code></h3>

Sequence of all sub-modules.

Submodules are modules which are properties of this module, or found as
properties of modules which are properties of this module (and so on).

```
>>> a = tf.Module()
>>> b = tf.Module()
>>> c = tf.Module()
>>> a.b = b
>>> b.c = c
>>> list(a.submodules) == [b, c]
True
>>> list(b.submodules) == [c]
True
>>> list(c.submodules) == []
True
```

#### Returns:

A sequence of all submodules.


<h3 id="trainable_variables"><code>trainable_variables</code></h3>

Sequence of trainable variables owned by this module and its submodules.

Note: this method uses reflection to find variables on the current instance
and submodules. For performance reasons you may wish to cache the result
of calling this method if you don't expect the return value to change.

#### Returns:

A sequence of variables for the current module (sorted by attribute
name) followed by variables from all submodules recursively (breadth
first).


<h3 id="variables"><code>variables</code></h3>

Sequence of variables owned by this module and its submodules.

Note: this method uses reflection to find variables on the current instance
and submodules. For performance reasons you may wish to cache the result
of calling this method if you don't expect the return value to change.

#### Returns:

A sequence of variables for the current module (sorted by attribute
name) followed by variables from all submodules recursively (breadth
first).




## Methods

<h3 id="with_name_scope"><code>with_name_scope</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/module/module.py">View source</a>

``` python
@classmethod
with_name_scope(
    cls,
    method
)
```

Decorator to automatically enter the module name scope.

```
>>> class MyModule(tf.Module):
...   @tf.Module.with_name_scope
...   def __call__(self, x):
...     if not hasattr(self, 'w'):
...       self.w = tf.Variable(tf.random.normal([x.shape[1], 3]))
...     return tf.matmul(x, self.w)
```

Using the above module would produce <a href="../tf/Variable.md"><code>tf.Variable</code></a>s and <a href="../tf/Tensor.md"><code>tf.Tensor</code></a>s whose
names included the module name:

```
>>> mod = MyModule()
>>> mod(tf.ones([1, 2]))
<tf.Tensor: shape=(1, 3), dtype=float32, numpy=..., dtype=float32)>
>>> mod.w
<tf.Variable 'my_module/Variable:0' shape=(2, 3) dtype=float32,
numpy=..., dtype=float32)>
```

#### Args:


* <b>`method`</b>: The method to wrap.


#### Returns:

The original method wrapped such that it enters the module's name scope.






## Compat aliases

* `tf.compat.v1.Module`
* `tf.compat.v2.Module`

