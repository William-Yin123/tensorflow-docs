<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.data.experimental.unique" />
<meta itemprop="path" content="Stable" />
</div>

# tf.data.experimental.unique

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/data/experimental/ops/unique.py">View source</a>



Creates a `Dataset` from another `Dataset`, discarding duplicates.

``` python
tf.data.experimental.unique()
```



<!-- Placeholder for "Used in" -->

Use this transformation to produce a dataset that contains one instance of
each unique element in the input. For example:

```python
dataset = tf.data.Dataset.from_tensor_slices([1, 37, 2, 37, 2, 1])

# Using `unique()` will drop the duplicate elements.
dataset = dataset.apply(tf.data.experimental.unique())  # ==> { 1, 37, 2 }
```

#### Returns:

A `Dataset` transformation function, which can be passed to
<a href="../../../tf/data/Dataset.md#apply"><code>tf.data.Dataset.apply</code></a>.


## Compat aliases

* `tf.compat.v1.data.experimental.unique`
* `tf.compat.v2.data.experimental.unique`

