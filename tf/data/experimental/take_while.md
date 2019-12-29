<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.data.experimental.take_while" />
<meta itemprop="path" content="Stable" />
</div>

# tf.data.experimental.take_while

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/data/experimental/ops/take_while_ops.py">View source</a>



A transformation that stops dataset iteration based on a `predicate`.

``` python
tf.data.experimental.take_while(predicate)
```



<!-- Placeholder for "Used in" -->


#### Args:


* <b>`predicate`</b>: A function that maps a nested structure of tensors (having shapes
  and types defined by `self.output_shapes` and `self.output_types`) to a
  scalar <a href="../../../tf.md#bool"><code>tf.bool</code></a> tensor.


#### Returns:

A `Dataset` transformation function, which can be passed to
<a href="../../../tf/data/Dataset.md#apply"><code>tf.data.Dataset.apply</code></a>.


## Compat aliases

* `tf.compat.v1.data.experimental.take_while`
* `tf.compat.v2.data.experimental.take_while`

