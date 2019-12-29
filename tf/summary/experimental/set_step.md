<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.summary.experimental.set_step" />
<meta itemprop="path" content="Stable" />
</div>

# tf.summary.experimental.set_step

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/summary_ops_v2.py">View source</a>



Sets the default summary step for the current thread.

``` python
tf.summary.experimental.set_step(step)
```



<!-- Placeholder for "Used in" -->

For convenience, this function sets a default value for the `step` parameter
used in summary-writing functions elsewhere in the API so that it need not
be explicitly passed in every such invocation. The value can be a constant
or a variable, and can be retrieved via <a href="../../../tf/summary/experimental/get_step.md"><code>tf.summary.experimental.get_step()</code></a>.

Note: when using this with @tf.functions, the step value will be captured at
the time the function is traced, so changes to the step outside the function
will not be reflected inside the function unless using a <a href="../../../tf/Variable.md"><code>tf.Variable</code></a> step.

#### Args:


* <b>`step`</b>: An `int64`-castable default step value, or None to unset.

## Compat aliases

* `tf.compat.v2.summary.experimental.set_step`

