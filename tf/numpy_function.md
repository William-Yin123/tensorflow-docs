<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.numpy_function" />
<meta itemprop="path" content="Stable" />
</div>

# tf.numpy_function

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/script_ops.py">View source</a>



Wraps a python function and uses it as a TensorFlow op.

``` python
tf.numpy_function(
    func,
    inp,
    Tout,
    name=None
)
```



<!-- Placeholder for "Used in" -->

Given a python function `func` wrap this function as an operation in a
TensorFlow function. `func` must take numpy arrays as its arguments and
return numpy arrays as its outputs.

The following example creates a TensorFlow graph with `np.sinh()` as an
operation in the graph:

```
>>> def my_numpy_func(x):
...   # x will be a numpy array with the contents of the input to the
...   # tf.function
...   return np.sinh(x)
>>> @tf.function(input_signature=[tf.TensorSpec(None, tf.float32)])
... def tf_function(input):
...   y = tf.numpy_function(my_numpy_func, [input], tf.float32)
...   return y * y
>>> tf_function(tf.constant(1.))
<tf.Tensor: shape=(), dtype=float32, numpy=1.3810978>
```

Comparison to <a href="../tf/py_function.md"><code>tf.py_function</code></a>:
<a href="../tf/py_function.md"><code>tf.py_function</code></a> and <a href="../tf/numpy_function.md"><code>tf.numpy_function</code></a> are very similar, except that
<a href="../tf/numpy_function.md"><code>tf.numpy_function</code></a> takes numpy arrays, and not <a href="../tf/Tensor.md"><code>tf.Tensor</code></a>s. If you want the
function to contain `tf.Tensors`, and have any TensorFlow operations executed
in the function be differentiable, please use <a href="../tf/py_function.md"><code>tf.py_function</code></a>.

Note: The <a href="../tf/numpy_function.md"><code>tf.numpy_function</code></a> operation has the following known
limitations:

* The body of the function (i.e. `func`) will not be serialized in a
  `tf.SavedModel`. Therefore, you should not use this function if you need to
  serialize your model and restore it in a different environment.

* The operation must run in the same address space as the Python program
  that calls <a href="../tf/numpy_function.md"><code>tf.numpy_function()</code></a>. If you are using distributed
  TensorFlow, you must run a <a href="../tf/distribute/Server.md"><code>tf.distribute.Server</code></a> in the same process as the
  program that calls <a href="../tf/numpy_function.md"><code>tf.numpy_function</code></a>  you must pin the created
  operation to a device in that server (e.g. using `with tf.device():`).

* Since the function takes numpy arrays, you cannot take gradients
  through a numpy_function. If you require something that is differentiable,
  please consider using tf.py_function.

#### Args:


* <b>`func`</b>: A Python function, which accepts `numpy.ndarray` objects as arguments
  and returns a list of `numpy.ndarray` objects (or a single
  `numpy.ndarray`). This function must accept as many arguments as there are
  tensors in `inp`, and these argument types will match the corresponding
  <a href="../tf/Tensor.md"><code>tf.Tensor</code></a> objects in `inp`. The returns `numpy.ndarray`s must match the
  number and types defined `Tout`.
  Important Note: Input and output `numpy.ndarray`s of `func` are not
    guaranteed to be copies. In some cases their underlying memory will be
    shared with the corresponding TensorFlow tensors. In-place modification
    or storing `func` input or return values in python datastructures
    without explicit (np.)copy can have non-deterministic consequences.
* <b>`inp`</b>: A list of <a href="../tf/Tensor.md"><code>tf.Tensor</code></a> objects.
* <b>`Tout`</b>: A list or tuple of tensorflow data types or a single tensorflow data
  type if there is only one, indicating what `func` returns.
stateful (bool): If True, the function should be considered stateful. If
  a function is stateless, when given the same input it will return the same
  output and have no observable side effects. Optimizations such as common
  subexpression elimination are only performed on stateless operations.
* <b>`name`</b>: (Optional) A name for the operation.


#### Returns:

Single or list of <a href="../tf/Tensor.md"><code>tf.Tensor</code></a> which `func` computes.


## Compat aliases

* `tf.compat.v1.numpy_function`
* `tf.compat.v2.numpy_function`

