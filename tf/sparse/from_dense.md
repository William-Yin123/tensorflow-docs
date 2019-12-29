<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.sparse.from_dense" />
<meta itemprop="path" content="Stable" />
</div>

# tf.sparse.from_dense

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/sparse_ops.py">View source</a>



Converts a dense tensor into a sparse tensor.

``` python
tf.sparse.from_dense(
    tensor,
    name=None
)
```



<!-- Placeholder for "Used in" -->

Only elements not equal to zero will be present in the result. The resulting
`SparseTensor` has the same dtype and shape as the input.

#### Args:


* <b>`tensor`</b>: A dense `Tensor` to be converted to a `SparseTensor`.
* <b>`name`</b>: Optional name for the op.


#### Returns:

The `SparseTensor`.


## Compat aliases

* `tf.compat.v1.sparse.from_dense`
* `tf.compat.v2.sparse.from_dense`

