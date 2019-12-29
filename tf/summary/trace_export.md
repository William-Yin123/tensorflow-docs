<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.summary.trace_export" />
<meta itemprop="path" content="Stable" />
</div>

# tf.summary.trace_export

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/summary_ops_v2.py">View source</a>



Stops and exports the active trace as a Summary and/or profile file.

``` python
tf.summary.trace_export(
    name,
    step=None,
    profiler_outdir=None
)
```



<!-- Placeholder for "Used in" -->

Stops the trace and exports all metadata collected during the trace to the
default SummaryWriter, if one has been set.

#### Args:


* <b>`name`</b>: A name for the summary to be written.
* <b>`step`</b>: Explicit `int64`-castable monotonic step value for this summary. If
  omitted, this defaults to <a href="../../tf/summary/experimental/get_step.md"><code>tf.summary.experimental.get_step()</code></a>, which must
  not be None.
* <b>`profiler_outdir`</b>: Output directory for profiler. It is required when profiler
  is enabled when trace was started. Otherwise, it is ignored.


#### Raises:


* <b>`ValueError`</b>: if a default writer exists, but no step was provided and
  <a href="../../tf/summary/experimental/get_step.md"><code>tf.summary.experimental.get_step()</code></a> is None.

## Compat aliases

* `tf.compat.v2.summary.trace_export`

