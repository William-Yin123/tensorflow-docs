<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.data.experimental.get_next_as_optional" />
<meta itemprop="path" content="Stable" />
</div>

# tf.data.experimental.get_next_as_optional

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/data/ops/iterator_ops.py">View source</a>



Returns an `Optional` that contains the next value from the iterator.

``` python
tf.data.experimental.get_next_as_optional(iterator)
```



<!-- Placeholder for "Used in" -->

If `iterator` has reached the end of the sequence, the returned `Optional`
will have no value.

#### Args:


* <b>`iterator`</b>: A <a href="../../../tf/compat/v1/data/Iterator.md"><code>tf.compat.v1.data.Iterator</code></a> object.


#### Returns:

An `Optional` object representing the next value from the iterator (if it
has one) or no value.


## Compat aliases

* `tf.compat.v1.data.experimental.get_next_as_optional`
* `tf.compat.v2.data.experimental.get_next_as_optional`
