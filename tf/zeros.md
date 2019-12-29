<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.zeros" />
<meta itemprop="path" content="Stable" />
</div>

# tf.zeros

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/array_ops.py">View source</a>



Creates a tensor with all elements set to zero.

``` python
tf.zeros(
    shape,
    dtype=tf.dtypes.float32,
    name=None
)
```



<!-- Placeholder for "Used in" -->

This operation returns a tensor of type `dtype` with shape `shape` and
all elements set to zero.

```
>>> tf.zeros([3, 4], tf.int32)
<tf.Tensor: shape=(3, 4), dtype=int32, numpy=
array([[0, 0, 0, 0],
       [0, 0, 0, 0],
       [0, 0, 0, 0]], dtype=int32)>
```

#### Args:


* <b>`shape`</b>: A `list` of integers, a `tuple` of integers, or
  a 1-D `Tensor` of type `int32`.
* <b>`dtype`</b>: The DType of an element in the resulting `Tensor`.
* <b>`name`</b>: Optional string. A name for the operation.


#### Returns:

A `Tensor` with all elements set to zero.


## Compat aliases

* `tf.compat.v1.zeros`
* `tf.compat.v2.zeros`

