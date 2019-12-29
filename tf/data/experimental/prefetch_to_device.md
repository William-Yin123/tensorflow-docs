<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.data.experimental.prefetch_to_device" />
<meta itemprop="path" content="Stable" />
</div>

# tf.data.experimental.prefetch_to_device

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/data/experimental/ops/prefetching_ops.py">View source</a>



A transformation that prefetches dataset values to the given `device`.

``` python
tf.data.experimental.prefetch_to_device(
    device,
    buffer_size=None
)
```



<!-- Placeholder for "Used in" -->

NOTE: Although the transformation creates a <a href="../../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a>, the
transformation must be the final `Dataset` in the input pipeline.

#### Args:


* <b>`device`</b>: A string. The name of a device to which elements will be prefetched.
* <b>`buffer_size`</b>: (Optional.) The number of elements to buffer on `device`.
  Defaults to an automatically chosen value.


#### Returns:

A `Dataset` transformation function, which can be passed to
<a href="../../../tf/data/Dataset.md#apply"><code>tf.data.Dataset.apply</code></a>.


## Compat aliases

* `tf.compat.v1.data.experimental.prefetch_to_device`
* `tf.compat.v2.data.experimental.prefetch_to_device`

