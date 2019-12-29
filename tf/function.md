<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.function" />
<meta itemprop="path" content="Stable" />
</div>

# tf.function

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/eager/def_function.py">View source</a>



Compiles a function into a callable TensorFlow graph.

``` python
tf.function(
    func=None,
    input_signature=None,
    autograph=True,
    experimental_implements=None,
    experimental_autograph_options=None,
    experimental_relax_shapes=False,
    experimental_compile=None
)
```



<!-- Placeholder for "Used in" -->

<a href="../tf/function.md"><code>tf.function</code></a> constructs a callable that executes a TensorFlow graph
(<a href="../tf/Graph.md"><code>tf.Graph</code></a>) created by trace-compiling the TensorFlow operations in `func`,
effectively executing `func` as a TensorFlow graph.

#### Example usage:



```
>>> @tf.function
... def f(x, y):
...   return x ** 2 + y
>>> x = tf.constant([2, 3])
>>> y = tf.constant([3, -2])
>>> f(x, y)
<tf.Tensor: ... numpy=array([7, 7], ...)>
```

_Features_

`func` may use data-dependent control flow, including `if`, `for`, `while`
`break`, `continue` and `return` statements:

```
>>> @tf.function
... def f(x):
...   if tf.reduce_sum(x) > 0:
...     return x * x
...   else:
...     return -x // 2
>>> f(tf.constant(-2))
<tf.Tensor: ... numpy=1>
```

`func`'s closure may include <a href="../tf/Tensor.md"><code>tf.Tensor</code></a> and <a href="../tf/Variable.md"><code>tf.Variable</code></a> objects:

```
>>> @tf.function
... def f():
...   return x ** 2 + y
>>> x = tf.constant([-2, -3])
>>> y = tf.Variable([3, -2])
>>> f()
<tf.Tensor: ... numpy=array([7, 7], ...)>
```

`func` may also use ops with side effects, such as <a href="../tf/print.md"><code>tf.print</code></a>, <a href="../tf/Variable.md"><code>tf.Variable</code></a>
and others:

```
>>> v = tf.Variable(1)
>>> @tf.function
... def f(x):
...   for i in tf.range(x):
...     v.assign_add(i)
>>> f(3)
>>> v
<tf.Variable ... numpy=4>
```

Important: Any Python side-effects (appending to a list, printing with
`print`, etc) will only happen once, when `func` is traced. To have
side-effects executed into your <a href="../tf/function.md"><code>tf.function</code></a> they need to be written
as TF ops:

```
>>> l = []
>>> @tf.function
... def f(x):
...   for i in x:
...     l.append(i + 1)    # Caution! Will only happen once when tracing
>>> f(tf.constant([1, 2, 3]))
>>> l
[<tf.Tensor ...>]
```

Instead, use TensorFlow collections like <a href="../tf/TensorArray.md"><code>tf.TensorArray</code></a>:

```
>>> @tf.function
... def f(x):
...   ta = tf.TensorArray(dtype=tf.int32, size=0, dynamic_size=True)
...   for i in range(len(x)):
...     ta = ta.write(i, x[i] + 1)
...   return ta.stack()
>>> f(tf.constant([1, 2, 3]))
<tf.Tensor: ..., numpy=array([2, 3, 4], ...)>
```

_<a href="../tf/function.md"><code>tf.function</code></a> is polymorphic_

Internally, <a href="../tf/function.md"><code>tf.function</code></a> can build more than one graph, to support arguments
with different data types or shapes, since TensorFlow can build more
efficient graphs that are specialized on shapes and dtypes. <a href="../tf/function.md"><code>tf.function</code></a>
also treats any pure Python value as opaque objects, and builds a separate
graph for each set of Python arguments that it encounters.

To obtain an individual graph, use the `get_concrete_function` method of
the callable created by <a href="../tf/function.md"><code>tf.function</code></a>. It can be called with the same
arguments as `func` and returns a special <a href="../tf/Graph.md"><code>tf.Graph</code></a> object:

```
>>> @tf.function
... def f(x):
...   return x + 1
>>> isinstance(f.get_concrete_function(1).graph, tf.Graph)
True
```

Caution: Passing python scalars or lists as arguments to <a href="../tf/function.md"><code>tf.function</code></a> will
always build a new graph. To avoid this, pass numeric arguments as Tensors
whenever possible:

```
>>> @tf.function
... def f(x):
...   return tf.abs(x)
>>> f1 = f.get_concrete_function(1)
>>> f2 = f.get_concrete_function(2)  # Slow - builds new graph
>>> f1 is f2
False
>>> f1 = f.get_concrete_function(tf.constant(1))
>>> f2 = f.get_concrete_function(tf.constant(2))  # Fast - reuses f1
>>> f1 is f2
True
```

Python numerical arguments should only be used when they take few distinct
values, such as hyperparameters like the number of layers in a neural network.

_Input signatures_

For Tensor arguments, <a href="../tf/function.md"><code>tf.function</code></a> instantiates a separate graph for every
unique set of input shapes and datatypes. The example below creates two
separate graphs, each specialized to a different shape:

```
>>> @tf.function
... def f(x):
...   return x + 1
>>> vector = tf.constant([1.0, 1.0])
>>> matrix = tf.constant([[3.0]])
>>> f.get_concrete_function(vector) is f.get_concrete_function(matrix)
False
```

An "input signature" can be optionally provided to <a href="../tf/function.md"><code>tf.function</code></a> to control
the graphs traced. The input signature specifies the shape and type of each
Tensor argument to the function using a <a href="../tf/TensorSpec.md"><code>tf.TensorSpec</code></a> object. More general
shapes can be used. This is useful to avoid creating multiple graphs when
Tensors have dynamic shapes. It also restricts the dhape and datatype of
Tensors that can be used:

```
>>> @tf.function(
...     input_signature=[tf.TensorSpec(shape=None, dtype=tf.float32)])
... def f(x):
...   return x + 1
>>> vector = tf.constant([1.0, 1.0])
>>> matrix = tf.constant([[3.0]])
>>> f.get_concrete_function(vector) is f.get_concrete_function(matrix)
True
```

_Variables may only be created once_

<a href="../tf/function.md"><code>tf.function</code></a> only allows creating new <a href="../tf/Variable.md"><code>tf.Variable</code></a> objects when it is called
for the first time:

```
>>> class MyModule(tf.Module):
...   def __init__(self):
...     self.v = None
...
...   @tf.function
...   def call(self, x):
...     if self.v is None:
...       self.v = tf.Variable(tf.ones_like(x))
...     return self.v * x
```

In general, it is recommended to create stateful objects like <a href="../tf/Variable.md"><code>tf.Variable</code></a>
outside of <a href="../tf/function.md"><code>tf.function</code></a> and passing them as arguments.

#### Args:


* <b>`func`</b>: the function to be compiled. If `func` is None, <a href="../tf/function.md"><code>tf.function</code></a> returns
  a decorator that can be invoked with a single argument - `func`. In other
  words, `tf.function(input_signature=...)(func)` is equivalent to
  <a href="../tf/function.md"><code>tf.function(func, input_signature=...)</code></a>. The former can be used as
  decorator.
* <b>`input_signature`</b>: A possibly nested sequence of <a href="../tf/TensorSpec.md"><code>tf.TensorSpec</code></a> objects
  specifying the shapes and dtypes of the Tensors that will be supplied to
  this function. If `None`, a separate function is instantiated for each
  inferred input signature.  If input_signature is specified, every input to
  `func` must be a `Tensor`, and `func` cannot accept `**kwargs`.
* <b>`autograph`</b>: Whether autograph should be applied on `func` before tracing a
  graph. Data-dependent control flow requires `autograph=True`. For more
  information, see the [tf.function and AutoGraph guide](
  https://www.tensorflow.org/guide/function).
* <b>`experimental_implements`</b>: If provided, contains a name of a "known" function
  this implements. For example "mycompany.my_recurrent_cell".
  This is stored as an attribute in inference function,
  which can then be detected when processing serialized function.
  See
  https://github.com/tensorflow/community/blob/master/rfcs/20190610-standardizing-composite_ops.md
  for details.  For an example of utilizing this attribute see:
  https://github.com/tensorflow/tensorflow/blob/master/tensorflow/compiler/mlir/lite/transforms/prepare_composite_functions_tf.cc
  The code above automatically detects and substitutes function that
  implements "embedded_matmul" and allows TFLite to substitute its own
  implementations. For instance, a tensorflow user can use this
   attribute to mark that their function also implements
  `embedded_matmul``` (perhaps more efficiently!)
  by specifying it using this flag.

    ```python
    @tf.function(experimental_implements="embedded_matmul"):
    def embedding_matmul(a, b):
       # custom implementation here
    ```

* <b>`experimental_autograph_options`</b>: Optional tuple of
  `tf.autograph.experimental.Feature` values.
* <b>`experimental_relax_shapes`</b>: When True, `tf.function` may generate fewer,
  graphs that are less specialized on input shapes.
* <b>`experimental_compile`</b>: If True, the function is always compiled by
  [XLA](https://www.tensorflow.org/xla). XLA may be more efficient in some
  cases (e.g. TPU, XLA_GPU, dense tensor computations).


#### Returns:

If `func` is not None, returns a callable that will execute the compiled
function (and return zero or more `tf.Tensor` objects).
If `func` is None, returns a decorator that, when invoked with a single
`func` argument, returns a callable equivalent to the case above.


## Compat aliases

* `tf.compat.v1.function`
* `tf.compat.v2.function`

