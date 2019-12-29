<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.autograph.to_graph" />
<meta itemprop="path" content="Stable" />
</div>

# tf.autograph.to_graph

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/autograph/impl/api.py">View source</a>



Converts a Python entity into a TensorFlow graph.

``` python
tf.autograph.to_graph(
    entity,
    recursive=True,
    experimental_optional_features=None
)
```



<!-- Placeholder for "Used in" -->

Also see: <a href="../../tf/autograph/to_code.md"><code>tf.autograph.to_code</code></a>, <a href="../../tf/function.md"><code>tf.function</code></a>.

Unlike <a href="../../tf/function.md"><code>tf.function</code></a>, `to_graph` is a low-level transpiler that converts
Python code to TensorFlow graph code. It does not implement any caching,
variable management or create any actual ops, and is best used where greater
control over the generated TensorFlow graph is desired. Another difference
from <a href="../../tf/function.md"><code>tf.function</code></a> is that `to_graph` will not wrap the graph into a
TensorFlow function or a Python callable. Internally, <a href="../../tf/function.md"><code>tf.function</code></a> uses
`to_graph`.

#### Example usage:



```
>>> def f(x):
...   if x > 0:
...     y = x * x
...   else:
...     y = -x
...   return y
...
>>> converted_f = to_graph(f)
>>> x = tf.constant(2)
>>> converted_f(x)  # converted_foo is like a TensorFlow Op.
<tf.Tensor: shape=(), dtype=int32, numpy=4>
```

Supported Python entities include:
  * functions
  * classes
  * object methods

Functions are converted into new functions with converted code.

Classes are converted by generating a new class whose methods use converted
code.

Methods are converted into unbound function that have an additional first
argument called `self`.

For a tutorial, see the
[tf.function and AutoGraph guide](https://www.tensorflow.org/guide/function).
For more detailed information, see the
[AutoGraph reference documentation](https://github.com/tensorflow/tensorflow/blob/master/tensorflow/python/autograph/g3doc/reference/index.md).

#### Args:


* <b>`entity`</b>: Python callable or class to convert.
* <b>`recursive`</b>: Whether to recursively convert any functions that the converted
  function may call.
* <b>`experimental_optional_features`</b>: `None`, a tuple of, or a single
  <a href="../../tf/autograph/experimental/Feature.md"><code>tf.autograph.experimental.Feature</code></a> value.


#### Returns:

Same as `entity`, the converted Python function or class.



#### Raises:


* <b>`ValueError`</b>: If the entity could not be converted.

## Compat aliases

* `tf.compat.v2.autograph.to_graph`

