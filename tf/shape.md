<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.shape" />
<meta itemprop="path" content="Stable" />
</div>

# tf.shape

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/array_ops.py">View source</a>



Returns the shape of a tensor.

``` python
tf.shape(
    input,
    out_type=tf.dtypes.int32,
    name=None
)
```



<!-- Placeholder for "Used in" -->

This operation returns a 1-D integer tensor representing the shape of `input`.
This represents the minimal set of known information at definition time.

#### For example:



```
>>> t = tf.constant([[[1, 1, 1], [2, 2, 2]], [[3, 3, 3], [4, 4, 4]]])
>>> tf.shape(t)
<tf.Tensor: shape=(3,), dtype=int32, numpy=array([2, 2, 3], dtype=int32)>
>>> tf.shape(t).numpy()
array([2, 2, 3], dtype=int32)
```

Note: When using symbolic tensors, such as when using the Keras functional
API, tf.shape() will return the shape of the symbolic tensor.

```
>>> a = tf.keras.layers.Input((None, 10))
>>> tf.shape(a)
<tf.Tensor ... shape=(3,) dtype=int32>
```

In these cases, using <a href="../tf/Tensor.md#shape"><code>tf.Tensor.shape</code></a> will return more informative results.

```
>>> a.shape
TensorShape([None, None, 10])
```

<a href="../tf/shape.md"><code>tf.shape</code></a> and <a href="../tf/Tensor.md#shape"><code>Tensor.shape</code></a> should be identical in eager mode.  Within
<a href="../tf/function.md"><code>tf.function</code></a> or within a <a href="../tf/compat/v1.md"><code>compat.v1</code></a> context, not all dimensions may be
known until execution time.

#### Args:


* <b>`input`</b>: A `Tensor` or `SparseTensor`.
* <b>`out_type`</b>: (Optional) The specified output type of the operation (`int32` or
  `int64`). Defaults to <a href="../tf.md#int32"><code>tf.int32</code></a>.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `out_type`.


## Compat aliases

* `tf.compat.v2.shape`

