<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.data.get_output_types" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.data.get_output_types

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/data/ops/dataset_ops.py">View source</a>



Returns the output shapes of a `Dataset` or `Iterator` elements.

``` python
tf.compat.v1.data.get_output_types(dataset_or_iterator)
```



<!-- Placeholder for "Used in" -->

This utility method replaces the deprecated-in-V2
`tf.compat.v1.Dataset.output_types` property.

#### Args:


* <b>`dataset_or_iterator`</b>: A <a href="../../../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a> or `tf.data.Iterator`.


#### Returns:

A nested structure of <a href="../../../../tf/dtypes/DType.md"><code>tf.DType</code></a> objects objects matching the structure of
dataset / iterator elements and specifying the shape of the individual
components.


