<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.data.make_one_shot_iterator" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.data.make_one_shot_iterator

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/data/ops/dataset_ops.py">View source</a>



Creates a <a href="../../../../tf/compat/v1/data/Iterator.md"><code>tf.compat.v1.data.Iterator</code></a> for enumerating the elements of a dataset.

``` python
tf.compat.v1.data.make_one_shot_iterator(dataset)
```



<!-- Placeholder for "Used in" -->

Note: The returned iterator will be initialized automatically.
A "one-shot" iterator does not support re-initialization.

#### Args:


* <b>`dataset`</b>: A <a href="../../../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a>.


#### Returns:

A <a href="../../../../tf/compat/v1/data/Iterator.md"><code>tf.compat.v1.data.Iterator</code></a> over the elements of this dataset.


