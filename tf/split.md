<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.split" />
<meta itemprop="path" content="Stable" />
</div>

# tf.split

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/array_ops.py">View source</a>



Splits a tensor into sub tensors.

``` python
tf.split(
    value,
    num_or_size_splits,
    axis=0,
    num=None,
    name='split'
)
```



<!-- Placeholder for "Used in" -->

If `num_or_size_splits` is an integer, then `value` is split along dimension
`axis` into `num_split` smaller tensors. This requires that `num_split` evenly
divides `value.shape[axis]`.

If `num_or_size_splits` is a 1-D Tensor (or list), we call it `size_splits`
and `value` is split into `len(size_splits)` elements. The shape of the `i`-th
element has the same size as the `value` except along dimension `axis` where
the size is `size_splits[i]`.

#### For example:



Split `x` into 3 tensors along dimension 1

```
>>> x = tf.Variable(tf.random.uniform([5, 30], -1, 1))
>>> s0, s1, s2 = tf.split(x, num_or_size_splits=3, axis=1)
>>> tf.shape(s0).numpy()
array([ 5, 10], dtype=int32)
```

Split `x` into 3 tensors with sizes [4, 15, 11] along dimension 1

```
>>> split0, split1, split2 = tf.split(x, [4, 15, 11], 1)
>>> tf.shape(split0).numpy()
array([5, 4], dtype=int32)
>>> tf.shape(split1).numpy()
array([ 5, 15], dtype=int32)
>>> tf.shape(split2).numpy()
array([ 5, 11], dtype=int32)
```

#### Args:


* <b>`value`</b>: The `Tensor` to split.
* <b>`num_or_size_splits`</b>: Either an integer indicating the number of splits along
  `axis` or a 1-D integer `Tensor` or Python list containing the sizes of
  each output tensor along `axis`. If a scalar, then it must evenly divide
  `value.shape[axis]`; otherwise the sum of sizes along the split axis
  must match that of the `value`.
* <b>`axis`</b>: An integer or scalar `int32` `Tensor`. The dimension along which to
  split. Must be in the range `[-rank(value), rank(value))`. Defaults to 0.
* <b>`num`</b>: Optional, used to specify the number of outputs when it cannot be
  inferred from the shape of `size_splits`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

if `num_or_size_splits` is a scalar returns `num_or_size_splits` `Tensor`
objects; if `num_or_size_splits` is a 1-D Tensor returns
`num_or_size_splits.get_shape[0]` `Tensor` objects resulting from splitting
`value`.



#### Raises:


* <b>`ValueError`</b>: If `num` is unspecified and cannot be inferred.

## Compat aliases

* `tf.compat.v1.split`
* `tf.compat.v2.split`

