<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.debugging.experimental.disable_dump_debug_info" />
<meta itemprop="path" content="Stable" />
</div>

# tf.debugging.experimental.disable_dump_debug_info

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/debug/lib/dumping_callback.py">View source</a>



Disable the currently-enabled debugging dumping.

``` python
tf.debugging.experimental.disable_dump_debug_info()
```



<!-- Placeholder for "Used in" -->

If the `enable_dump_debug_info()` method under the same Python namespace
has been invoked before, calling this method disables it. If no call to
`enable_dump_debug_info()` has been made, calling this method is a no-op.
Calling this method more than once is idempotent.

## Compat aliases

* `tf.compat.v1.debugging.experimental.disable_dump_debug_info`
* `tf.compat.v2.debugging.experimental.disable_dump_debug_info`

