<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.debugging.disable_check_numerics" />
<meta itemprop="path" content="Stable" />
</div>

# tf.debugging.disable_check_numerics

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/debug/lib/check_numerics_callback.py">View source</a>



Disable the eager/graph unified numerics checking mechanism.

``` python
tf.debugging.disable_check_numerics()
```



<!-- Placeholder for "Used in" -->

This method can be used after a call to <a href="../../tf/debugging/enable_check_numerics.md"><code>tf.debugging.enable_check_numerics()</code></a>
to disable the numerics-checking mechanism that catches inifnity and NaN
values output by ops executed eagerly or in tf.function-compiled graphs.

This method is idempotent. Calling it multiple times has the same effect
as calling it once.

This method takes effect only on the thread in which it is called.

## Compat aliases

* `tf.compat.v1.debugging.disable_check_numerics`
* `tf.compat.v2.debugging.disable_check_numerics`

