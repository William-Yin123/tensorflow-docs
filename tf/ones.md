<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.ones" />
<meta itemprop="path" content="Stable" />
</div>

# tf.ones

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/array_ops.py">View source</a>



Creates a tensor with all elements set to one (1).

``` python
tf.ones(
    shape,
    dtype=tf.dtypes.float32,
    name=None
)
```



<!-- Placeholder for "Used in" -->

This operation returns a tensor of type `dtype` with shape `shape` and
all elements set to one.

```
>>> tf.ones([3, 4], tf.int32)
<tf.Tensor: shape=(3, 4), dtype=int32, numpy=
array([[1, 1, 1, 1],
       [1, 1, 1, 1],
       [1, 1, 1, 1]], dtype=int32)>
```

#### Args:


* <b>`shape`</b>: A `list` of integers, a `tuple` of integers, or
  a 1-D `Tensor` of type `int32`.
* <b>`dtype`</b>: Optional DType of an element in the resulting `Tensor`. Default is
  <a href="../tf.md#float32"><code>tf.float32</code></a>.
* <b>`name`</b>: Optional string. A name for the operation.


#### Returns:

A `Tensor` with all elements set to one (1).


## Compat aliases

* `tf.compat.v1.ones`
* `tf.compat.v2.ones`

