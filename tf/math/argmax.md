<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.argmax" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.argmax

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/math_ops.py">View source</a>



Returns the index with the largest value across axes of a tensor.

**Aliases**: `tf.argmax`

``` python
tf.math.argmax(
    input,
    axis=None,
    output_type=tf.dtypes.int64,
    name=None
)
```



<!-- Placeholder for "Used in" -->

Note that in case of ties the identity of the return value is not guaranteed.

#### For example:



```
>>> A = tf.constant([2, 20, 30, 3, 6])
>>> tf.math.argmax(A)  # A[2] is maximum in tensor A
<tf.Tensor: shape=(), dtype=int64, numpy=2>
>>> B = tf.constant([[2, 20, 30, 3, 6], [3, 11, 16, 1, 8],
...                  [14, 45, 23, 5, 27]])
>>> tf.math.argmax(B, 0)
<tf.Tensor: shape=(5,), dtype=int64, numpy=array([2, 2, 0, 2, 2])>
>>> tf.math.argmax(B, 1)
<tf.Tensor: shape=(3,), dtype=int64, numpy=array([2, 2, 1])>
```

#### Args:


* <b>`input`</b>: A `Tensor`.
* <b>`axis`</b>: An integer, the axis to reduce across. Default to 0.
* <b>`output_type`</b>: An optional output dtype (<a href="../../tf.md#int32"><code>tf.int32</code></a> or <a href="../../tf.md#int64"><code>tf.int64</code></a>). Defaults
  to <a href="../../tf.md#int64"><code>tf.int64</code></a>.
* <b>`name`</b>: An optional name for the operation.


#### Returns:

A `Tensor` of type `output_type`.


## Compat aliases

* `tf.compat.v2.argmax`
* `tf.compat.v2.math.argmax`

