<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.config.experimental_run_functions_eagerly" />
<meta itemprop="path" content="Stable" />
</div>

# tf.config.experimental_run_functions_eagerly

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/eager/def_function.py">View source</a>



Enables / disables eager execution of <a href="../../tf/function.md"><code>tf.function</code></a>s.

``` python
tf.config.experimental_run_functions_eagerly(run_eagerly)
```



<!-- Placeholder for "Used in" -->

Calling <a href="../../tf/config/experimental_run_functions_eagerly.md"><code>tf.config.experimental_run_functions_eagerly(True)</code></a> will make all
invocations of <a href="../../tf/function.md"><code>tf.function</code></a> run eagerly instead of running as a traced graph
function.

This can be useful for debugging or profiling. For example, let's say you
implemented a simple iterative sqrt function, and you want to collect the
intermediate values and plot the convergence.  Appending the values to a list
in `@tf.function` normally wouldn't work since it will just record the Tensors
being traced, not the values.  Instead, you can do the following.

```
>>> ys = []
>>>
>>> @tf.function
... def sqrt(x):
...   y = x / 2
...   d = y
...   for _ in range(10):
...     d /= 2
...     if y * y < x:
...       y += d
...     else:
...       y -= d
...     ys.append(y.numpy())
...   return y
>>>
>>> tf.config.experimental_run_functions_eagerly(True)
>>> sqrt(tf.constant(2.))
<tf.Tensor: shape=(), dtype=float32, numpy=1.4150391>
>>> ys
[1.5, 1.25, 1.375, 1.4375, 1.40625, 1.421875, 1.4140625, 1.4179688, 1.4160156,
1.4150391]
>>> tf.config.experimental_run_functions_eagerly(False)
```

Calling <a href="../../tf/config/experimental_run_functions_eagerly.md"><code>tf.config.experimental_run_functions_eagerly(False)</code></a> will undo this
behavior.

#### Args:


* <b>`run_eagerly`</b>: Boolean. Whether to run functions eagerly.

## Compat aliases

* `tf.compat.v1.config.experimental_run_functions_eagerly`
* `tf.compat.v2.config.experimental_run_functions_eagerly`

