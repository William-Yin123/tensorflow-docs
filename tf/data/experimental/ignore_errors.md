<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.data.experimental.ignore_errors" />
<meta itemprop="path" content="Stable" />
</div>

# tf.data.experimental.ignore_errors

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/data/experimental/ops/error_ops.py">View source</a>



Creates a `Dataset` from another `Dataset` and silently ignores any errors.

``` python
tf.data.experimental.ignore_errors()
```



<!-- Placeholder for "Used in" -->

Use this transformation to produce a dataset that contains the same elements
as the input, but silently drops any elements that caused an error. For
example:

```python
dataset = tf.data.Dataset.from_tensor_slices([1., 2., 0., 4.])

# Computing `tf.debugging.check_numerics(1. / 0.)` will raise an
InvalidArgumentError.
dataset = dataset.map(lambda x: tf.debugging.check_numerics(1. / x, "error"))

# Using `ignore_errors()` will drop the element that causes an error.
dataset =
    dataset.apply(tf.data.experimental.ignore_errors())  # ==> {1., 0.5, 0.2}
```

#### Returns:

A `Dataset` transformation function, which can be passed to
<a href="../../../tf/data/Dataset.md#apply"><code>tf.data.Dataset.apply</code></a>.


## Compat aliases

* `tf.compat.v1.data.experimental.ignore_errors`
* `tf.compat.v2.data.experimental.ignore_errors`

