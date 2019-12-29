<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.data.experimental.enumerate_dataset" />
<meta itemprop="path" content="Stable" />
</div>

# tf.data.experimental.enumerate_dataset

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/data/experimental/ops/enumerate_ops.py">View source</a>



A transformation that enumerates the elements of a dataset. (deprecated)

``` python
tf.data.experimental.enumerate_dataset(start=0)
```



<!-- Placeholder for "Used in" -->

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Use `tf.data.Dataset.enumerate()

It is similar to python's `enumerate`.
For example:

```python
# NOTE: The following examples use `{ ... }` to represent the
# contents of a dataset.
a = { 1, 2, 3 }
b = { (7, 8), (9, 10) }

# The nested structure of the `datasets` argument determines the
# structure of elements in the resulting dataset.
a.apply(tf.data.experimental.enumerate_dataset(start=5))
=> { (5, 1), (6, 2), (7, 3) }
b.apply(tf.data.experimental.enumerate_dataset())
=> { (0, (7, 8)), (1, (9, 10)) }
```

#### Args:


* <b>`start`</b>: A <a href="../../../tf.md#int64"><code>tf.int64</code></a> scalar <a href="../../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing the start value for
  enumeration.


#### Returns:

A `Dataset` transformation function, which can be passed to
<a href="../../../tf/data/Dataset.md#apply"><code>tf.data.Dataset.apply</code></a>.


## Compat aliases

* `tf.compat.v1.data.experimental.enumerate_dataset`
* `tf.compat.v2.data.experimental.enumerate_dataset`

