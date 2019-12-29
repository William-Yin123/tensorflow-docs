<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.debugging.enable_check_numerics" />
<meta itemprop="path" content="Stable" />
</div>

# tf.debugging.enable_check_numerics

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/debug/lib/check_numerics_callback.py">View source</a>



Enable tensor numerics checking in an eager/graph unified fashion.

``` python
tf.debugging.enable_check_numerics(
    stack_height_limit=30,
    path_length_limit=50
)
```



<!-- Placeholder for "Used in" -->

The numerics checking mechanism will cause any TensorFlow eager execution or
graph execution to error out as soon as an op's output tensor contains
infinity or NaN.

This method is idempotent. Calling it multiple times has the same effect
as calling it once.

This method takes effect only on the thread in which it is called.

When a op's float-type output tensor contains any Infinity or NaN, an
<a href="../../tf/errors/InvalidArgumentError.md"><code>tf.errors.InvalidArgumentError</code></a> will be thrown, with an error message that
reveals the following information:
  - The type of the op that generated the tensor with bad numerics.
  - Data type (dtype) of the tensor.
  - Shape of the tensor (to the extent known at the time of eager execution
    or graph construction).
  - Name of the containing graph (if available).
  - (Graph mode only): The stack trace of the intra-graph op's creation,
    with a stack-height limit and a path-length limit for visual clarity.
    The stack frames that belong to the user's code (as opposed to
    tensorflow's internal code) are highlighted with a text arrow ("->").
  - (Eager mode only): How many of the offending tensor's elements are
    `Infinity` and `NaN`, respectively.

Once enabled, the check-numerics mechanism can be disabled by using
<a href="../../tf/debugging/disable_check_numerics.md"><code>tf.debugging.disable_check_numerics()</code></a>.

#### Example usage:



1. Catching infinity during the execution of a <a href="../../tf/function.md"><code>tf.function</code></a> graph:

   ```py
   import tensorflow as tf

   tf.debugging.enable_check_numerics()

   @tf.function
   def square_log_x_plus_1(x):
     v = tf.math.log(x + 1)
     return tf.math.square(v)

   x = -1.0

   # When the following line runs, a function graph will be compiled
   # from the Python function `log_x_plus_1()`. Due to the
   # `enable_check_numerics()` call above, the graph will contain
   # numerics checking ops that will run during the function graph's
   # execution. The function call generates an -infinity when the Log
   # (logarithm) op operates on the output tensor of the Add op.
   # The program errors out at this line, printing an error message.
   y = log_x_plus_1(x)
   z = -y
  ```

2. Catching NaN during eager execution:

   ```py
   import numpy as np
   import tensorflow as tf

   tf.debugging.enable_check_numerics()

   x = np.array([[0.0, -1.0], [4.0, 3.0]])

   # The following line executes the Sqrt op eagerly. Due to the negative
   # element in the input array, a NaN is generated. Due to the
   # `enable_check_numerics()` call above, the program errors immediately
   # at this line, printing an error message.
   y = tf.math.sqrt(x)
   z = tf.matmul(y, y)
   ```

#### Args:


* <b>`stack_height_limit`</b>: Limit to the height of the printed stack trace.
  Applicable only to ops in <a href="../../tf/function.md"><code>tf.function</code></a>s (graphs).
* <b>`path_length_limit`</b>: Limit to the file path included in the printed stack
  trace. Applicable only to ops in <a href="../../tf/function.md"><code>tf.function</code></a>s (graphs).

## Compat aliases

* `tf.compat.v1.debugging.enable_check_numerics`
* `tf.compat.v2.debugging.enable_check_numerics`

