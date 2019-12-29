<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.data.experimental.from_variant" />
<meta itemprop="path" content="Stable" />
</div>

# tf.data.experimental.from_variant

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/data/ops/dataset_ops.py">View source</a>



Constructs a dataset from the given variant and structure.

``` python
tf.data.experimental.from_variant(
    variant,
    structure
)
```



<!-- Placeholder for "Used in" -->


#### Args:


* <b>`variant`</b>: A scalar <a href="../../../tf.md#variant"><code>tf.variant</code></a> tensor representing a dataset.
* <b>`structure`</b>: A `tf.data.experimental.Structure` object representing the
  structure of each element in the dataset.


#### Returns:

A <a href="../../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a> instance.


## Compat aliases

* `tf.compat.v1.data.experimental.from_variant`
* `tf.compat.v2.data.experimental.from_variant`

