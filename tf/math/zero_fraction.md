<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.zero_fraction" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.zero_fraction

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/nn_impl.py">View source</a>



Returns the fraction of zeros in `value`.

**Aliases**: `tf.nn.zero_fraction`

``` python
tf.math.zero_fraction(
    value,
    name=None
)
```



<!-- Placeholder for "Used in" -->

If `value` is empty, the result is `nan`.

This is useful in summaries to measure and report sparsity.  For example,

```python
    z = tf.nn.relu(...)
    summ = tf.compat.v1.summary.scalar('sparsity', tf.nn.zero_fraction(z))
```

#### Args:


* <b>`value`</b>: A tensor of numeric type.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

The fraction of zeros in `value`, with type `float32`.


## Compat aliases

* `tf.compat.v1.math.zero_fraction`
* `tf.compat.v1.nn.zero_fraction`
* `tf.compat.v2.math.zero_fraction`
* `tf.compat.v2.nn.zero_fraction`

