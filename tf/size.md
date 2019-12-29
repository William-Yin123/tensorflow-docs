<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.size" />
<meta itemprop="path" content="Stable" />
</div>

# tf.size

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/array_ops.py">View source</a>



Returns the size of a tensor.

``` python
tf.size(
    input,
    out_type=tf.dtypes.int32,
    name=None
)
```



<!-- Placeholder for "Used in" -->

Returns a 0-D `Tensor` representing the number of elements in `input`
of type `out_type`. Defaults to tf.int32.

#### For example:



```
>>> t = tf.constant([[[1, 1, 1], [2, 2, 2]], [[3, 3, 3], [4, 4, 4]]])
>>> tf.size(t)
<tf.Tensor: shape=(), dtype=int32, numpy=12>
```

#### Args:


* <b>`input`</b>: A `Tensor` or `SparseTensor`.
* <b>`name`</b>: A name for the operation (optional).
* <b>`out_type`</b>: (Optional) The specified non-quantized numeric output type of the
  operation. Defaults to <a href="../tf.md#int32"><code>tf.int32</code></a>.


#### Returns:

A `Tensor` of type `out_type`. Defaults to <a href="../tf.md#int32"><code>tf.int32</code></a>.




#### Numpy Compatibility
Equivalent to np.size()



## Compat aliases

* `tf.compat.v2.size`

