<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.stack" />
<meta itemprop="path" content="Stable" />
</div>

# tf.stack

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/array_ops.py">View source</a>



Stacks a list of rank-`R` tensors into one rank-`(R+1)` tensor.

``` python
tf.stack(
    values,
    axis=0,
    name='stack'
)
```



<!-- Placeholder for "Used in" -->

Packs the list of tensors in `values` into a tensor with rank one higher than
each tensor in `values`, by packing them along the `axis` dimension.
Given a list of length `N` of tensors of shape `(A, B, C)`;

if `axis == 0` then the `output` tensor will have the shape `(N, A, B, C)`.
if `axis == 1` then the `output` tensor will have the shape `(A, N, B, C)`.
Etc.

#### For example:



```
>>> x = tf.constant([1, 4])
>>> y = tf.constant([2, 5])
>>> z = tf.constant([3, 6])
>>> tf.stack([x, y, z])
<tf.Tensor: shape=(3, 2), dtype=int32, numpy=
array([[1, 4],
       [2, 5],
       [3, 6]], dtype=int32)>
```

>> tf.stack([x, y, z], axis=1)
<tf.Tensor: shape=(2, 3), dtype=int32, numpy=
array([[1, 2, 3],
       [4, 5, 6]], dtype=int32)>

This is the opposite of unstack.  The numpy equivalent is `np.stack`

```
>>> np.array_equal(np.stack([x, y, z]), tf.stack([x, y, z]))
True
```

#### Args:


* <b>`values`</b>: A list of `Tensor` objects with the same shape and type.
* <b>`axis`</b>: An `int`. The axis to stack along. Defaults to the first dimension.
  Negative values wrap around, so the valid range is `[-(R+1), R+1)`.
* <b>`name`</b>: A name for this operation (optional).


#### Returns:


* <b>`output`</b>: A stacked `Tensor` with the same type as `values`.


#### Raises:


* <b>`ValueError`</b>: If `axis` is out of the range [-(R+1), R+1).

## Compat aliases

* `tf.compat.v1.stack`
* `tf.compat.v2.stack`

