<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.expand_dims" />
<meta itemprop="path" content="Stable" />
</div>

# tf.expand_dims

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/array_ops.py">View source</a>



Returns a tensor with an additional dimension inserted at index `axis`.

``` python
tf.expand_dims(
    input,
    axis,
    name=None
)
```



<!-- Placeholder for "Used in" -->

Given a tensor `input`, this operation inserts a dimension of size 1 at the
dimension index `axis` of `input`'s shape. The dimension index `axis` starts
at zero; if you specify a negative number for `axis` it is counted backward
from the end.

This operation is useful if you want to add a batch dimension to a single
element. For example, if you have a single image of shape `[height, width,
channels]`, you can make it a batch of one image with `expand_dims(image, 0)`,
which will make the shape `[1, height, width, channels]`.

#### Examples:



```
>>> t = [[1, 2, 3],[4, 5, 6]] # shape [2, 3]
```

```
>>> tf.expand_dims(t, 0)
<tf.Tensor: shape=(1, 2, 3), dtype=int32, numpy=
array([[[1, 2, 3],
        [4, 5, 6]]], dtype=int32)>
```

```
>>> tf.expand_dims(t, 1)
<tf.Tensor: shape=(2, 1, 3), dtype=int32, numpy=
array([[[1, 2, 3]],
       [[4, 5, 6]]], dtype=int32)>
```

```
>>> tf.expand_dims(t, 2)
<tf.Tensor: shape=(2, 3, 1), dtype=int32, numpy=
array([[[1],
        [2],
        [3]],
       [[4],
        [5],
        [6]]], dtype=int32)>
```

```
>>> tf.expand_dims(t, -1) # Last dimension index. In this case, same as 2.
<tf.Tensor: shape=(2, 3, 1), dtype=int32, numpy=
array([[[1],
        [2],
        [3]],
       [[4],
        [5],
        [6]]], dtype=int32)>
```

This operation is related to:

*   <a href="../tf/squeeze.md"><code>tf.squeeze</code></a>, which removes dimensions of size 1.
*   <a href="../tf/reshape.md"><code>tf.reshape</code></a>, which provides more flexible reshaping capability

#### Args:


* <b>`input`</b>: A `Tensor`.
* <b>`axis`</b>: Integer specifying the dimension index at which to expand the
  shape of `input`. Given an input of D dimensions, `axis` must be in range
  `[-(D+1), D]` (inclusive).
* <b>`name`</b>: Optional string. The name of the output `Tensor`.


#### Returns:

A tensor with the same data as `input`, with an additional dimension
inserted at the index specified by `axis`.



#### Raises:


* <b>`ValueError`</b>: If `axis` is not specified.
* <b>`InvalidArgumentError`</b>: If `axis` is out of range `[-(D+1), D]`.

## Compat aliases

* `tf.compat.v2.expand_dims`

