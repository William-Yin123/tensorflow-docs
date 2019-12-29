<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.fill" />
<meta itemprop="path" content="Stable" />
</div>

# tf.fill

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/array_ops.py">View source</a>



Creates a tensor filled with a scalar value.

``` python
tf.fill(
    dims,
    value,
    name=None
)
```



<!-- Placeholder for "Used in" -->

This operation creates a tensor of shape `dims` and fills it with `value`.

#### For example:



```
>>> tf.fill([2, 3], 9)
<tf.Tensor: shape=(2, 3), dtype=int32, numpy=
array([[9, 9, 9],
       [9, 9, 9]], dtype=int32)>
```

<a href="../tf/fill.md"><code>tf.fill</code></a> evaluates at graph runtime and supports dynamic shapes based on
other runtime `tf.Tensors`, unlike <a href="../tf/constant.md"><code>tf.constant(value, shape=dims)</code></a>, which
embeds the value as a `Const` node.

#### Args:


* <b>`dims`</b>: A 1-D sequence of non-negative numbers. Represents the shape of the
  output <a href="../tf/Tensor.md"><code>tf.Tensor</code></a>. Entries should be of type: `int32`, `int64`.
* <b>`value`</b>: A value to fill the returned <a href="../tf/Tensor.md"><code>tf.Tensor</code></a>.
* <b>`name`</b>: Optional string. The name of the output <a href="../tf/Tensor.md"><code>tf.Tensor</code></a>.


#### Returns:

A <a href="../tf/Tensor.md"><code>tf.Tensor</code></a> with shape `dims` and the same dtype as `value`.



#### Raises:


* <b>`InvalidArgumentError`</b>: `dims` contains negative entries.
* <b>`NotFoundError`</b>: `dims` contains non-integer entries.



#### Numpy Compatibility
Similar to `np.full`. In `numpy`, more parameters are supported. Passing a
number argument as the shape (`np.full(5, value)`) is valid in `numpy` for
specifying a 1-D shaped result, while TensorFlow does not support this syntax.



## Compat aliases

* `tf.compat.v1.fill`
* `tf.compat.v2.fill`

