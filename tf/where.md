<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.where" />
<meta itemprop="path" content="Stable" />
</div>

# tf.where

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/array_ops.py">View source</a>



Return the elements where `condition` is `True` (multiplexing `x` and `y`).

``` python
tf.where(
    condition,
    x=None,
    y=None,
    name=None
)
```



<!-- Placeholder for "Used in" -->

This operator has two modes: in one mode both `x` and `y` are provided, in
another mode neither are provided. `condition` is always expected to be a
<a href="../tf/Tensor.md"><code>tf.Tensor</code></a> of type `bool`.

#### Retrieving indices of `True` elements

If `x` and `y` are not provided (both are None):

<a href="../tf/where.md"><code>tf.where</code></a> will return the indices of `condition` that are `True`, in
the form of a 2-D tensor with shape (n, d).
(Where n is the number of matching indices in `condition`,
and d is the number of dimensions in `condition`).

Indices are output in row-major order.

```
>>> tf.where([True, False, False, True])
<tf.Tensor: shape=(2, 1), dtype=int64, numpy=
array([[0],
       [3]])>
```

```
>>> tf.where([[True, False], [False, True]])
<tf.Tensor: shape=(2, 2), dtype=int64, numpy=
array([[0, 0],
       [1, 1]])>
```

```
>>> tf.where([[[True, False], [False, True], [True, True]]])
<tf.Tensor: shape=(4, 3), dtype=int64, numpy=
array([[0, 0, 0],
       [0, 1, 1],
       [0, 2, 0],
       [0, 2, 1]])>
```

#### Multiplexing between `x` and `y`

If `x` and `y` are provided (both have non-None values):

<a href="../tf/where.md"><code>tf.where</code></a> will choose an output shape from the shapes of `condition`, `x`,
and `y` that all three shapes are
[broadcastable](https://docs.scipy.org/doc/numpy/reference/ufuncs.html) to.

The `condition` tensor acts as a mask that chooses whether the corresponding
element / row in the output should be taken from `x`
(if the elemment in `condition is True) or `y` (if it is false).

```
>>> tf.where([True, False, False, True], [1,2,3,4], [100,200,300,400])
<tf.Tensor: shape=(4,), dtype=int32, numpy=array([  1, 200, 300,   4],
dtype=int32)>
>>> tf.where([True, False, False, True], [1,2,3,4], [100])
<tf.Tensor: shape=(4,), dtype=int32, numpy=array([  1, 100, 100,   4],
dtype=int32)>
>>> tf.where([True, False, False, True], [1,2,3,4], 100)
<tf.Tensor: shape=(4,), dtype=int32, numpy=array([  1, 100, 100,   4],
dtype=int32)>
>>> tf.where([True, False, False, True], 1, 100)
<tf.Tensor: shape=(4,), dtype=int32, numpy=array([  1, 100, 100,   1],
dtype=int32)>
```

```
>>> tf.where(True, [1,2,3,4], 100)
<tf.Tensor: shape=(4,), dtype=int32, numpy=array([1, 2, 3, 4],
dtype=int32)>
>>> tf.where(False, [1,2,3,4], 100)
<tf.Tensor: shape=(4,), dtype=int32, numpy=array([100, 100, 100, 100],
dtype=int32)>
```

#### Args:


* <b>`condition`</b>: A <a href="../tf/Tensor.md"><code>tf.Tensor</code></a> of type `bool`
* <b>`x`</b>: If provided, a Tensor which is of the same type as `y`, and has a shape
  broadcastable with `condition` and `y`.
* <b>`y`</b>: If provided, a Tensor which is of the same type as `y`, and has a shape
  broadcastable with `condition` and `x`.
* <b>`name`</b>: A name of the operation (optional).


#### Returns:

If `x` and `y` are provided:
  A `Tensor` with the same type as `x` and `y`, and shape that
  is broadcast from `condition`, `x`, and `y`.
Otherwise, a `Tensor` with shape `(num_true, dim_size(condition))`.



#### Raises:


* <b>`ValueError`</b>: When exactly one of `x` or `y` is non-None, or the shapes
  are not all broadcastable.

## Compat aliases

* `tf.compat.v1.where_v2`
* `tf.compat.v2.where`

