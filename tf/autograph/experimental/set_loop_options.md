<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.autograph.experimental.set_loop_options" />
<meta itemprop="path" content="Stable" />
</div>

# tf.autograph.experimental.set_loop_options

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/autograph/lang/directives.py">View source</a>



Specifies additional arguments to be passed to the enclosing while_loop.

``` python
tf.autograph.experimental.set_loop_options(
    parallel_iterations=UNSPECIFIED,
    swap_memory=UNSPECIFIED,
    maximum_iterations=UNSPECIFIED,
    shape_invariants=UNSPECIFIED
)
```



<!-- Placeholder for "Used in" -->

The parameters apply to and only to the immediately enclosing loop. It only
has effect if the loop is staged as a TF while_loop; otherwise the parameters
have no effect.

#### Usage:


```
>>> @tf.function(autograph=True)
... def f():
...   n = 0
...   for i in tf.range(10):
...     tf.autograph.experimental.set_loop_options(maximum_iterations=3)
...     n += 1
...   return n
```

```
>>> @tf.function(autograph=True)
... def f():
...   v = tf.constant((0,))
...   for i in tf.range(3):
...     tf.autograph.experimental.set_loop_options(
...         shape_invariants=[(v, tf.TensorShape([None]))]
...     )
...     v = tf.concat((v, [i]), 0)
...   return v
```


Also see tf.while_loop.

#### Args:


* <b>`parallel_iterations`</b>: The maximum number of iterations allowed to run in
    parallel at any given time. Note that this does not guarantee parallel
    execution.
* <b>`swap_memory`</b>: Whether to store intermediate values needed for
    gradients on the CPU instead of GPU.
* <b>`maximum_iterations`</b>: Allows limiting the total number of iterations executed
    by the loop.
* <b>`shape_invariants`</b>: Allows controlling the argument with the same name passed
    to tf.while_loop. Unlike tf.while_loop, this is a list of
    `(tensor, shape)` pairs.

## Compat aliases

* `tf.compat.v1.autograph.experimental.set_loop_options`
* `tf.compat.v2.autograph.experimental.set_loop_options`

