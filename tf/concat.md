<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.concat" />
<meta itemprop="path" content="Stable" />
</div>

# tf.concat

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/array_ops.py">View source</a>



Concatenates tensors along one dimension.

``` python
tf.concat(
    values,
    axis,
    name='concat'
)
```



<!-- Placeholder for "Used in" -->

Concatenates the list of tensors `values` along dimension `axis`.  If
`values[i].shape = [D0, D1, ... Daxis(i), ...Dn]`, the concatenated
result has shape

    [D0, D1, ... Raxis, ...Dn]

where

    Raxis = sum(Daxis(i))

That is, the data from the input tensors is joined along the `axis`
dimension.

The number of dimensions of the input tensors must match, and all dimensions
except `axis` must be equal.

#### For example:



```
>>> t1 = [[1, 2, 3], [4, 5, 6]]
>>> t2 = [[7, 8, 9], [10, 11, 12]]
>>> concat([t1, t2], 0)
<tf.Tensor: shape=(4, 3), dtype=int32, numpy=
array([[ 1,  2,  3],
       [ 4,  5,  6],
       [ 7,  8,  9],
       [10, 11, 12]], dtype=int32)>
```

```
>>> concat([t1, t2], 1)
<tf.Tensor: shape=(2, 6), dtype=int32, numpy=
array([[ 1,  2,  3,  7,  8,  9],
       [ 4,  5,  6, 10, 11, 12]], dtype=int32)>
```

As in Python, the `axis` could also be negative numbers. Negative `axis`
are interpreted as counting from the end of the rank, i.e.,
 `axis + rank(values)`-th dimension.

#### For example:



```
>>> t1 = [[[1, 2], [2, 3]], [[4, 4], [5, 3]]]
>>> t2 = [[[7, 4], [8, 4]], [[2, 10], [15, 11]]]
>>> tf.concat([t1, t2], -1)
<tf.Tensor: shape=(2, 2, 4), dtype=int32, numpy=
  array([[[ 1,  2,  7,  4],
          [ 2,  3,  8,  4]],
         [[ 4,  4,  2, 10],
          [ 5,  3, 15, 11]]], dtype=int32)>
```

Note: If you are concatenating along a new axis consider using stack.
E.g.

```python
tf.concat([tf.expand_dims(t, axis) for t in tensors], axis)
```

can be rewritten as

```python
tf.stack(tensors, axis=axis)
```

#### Args:


* <b>`values`</b>: A list of `Tensor` objects or a single `Tensor`.
* <b>`axis`</b>: 0-D `int32` `Tensor`.  Dimension along which to concatenate. Must be
  in the range `[-rank(values), rank(values))`. As in Python, indexing for
  axis is 0-based. Positive axis in the rage of `[0, rank(values))` refers
  to `axis`-th dimension. And negative axis refers to `axis +
  rank(values)`-th dimension.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` resulting from concatenation of the input tensors.


## Compat aliases

* `tf.compat.v1.concat`
* `tf.compat.v2.concat`

