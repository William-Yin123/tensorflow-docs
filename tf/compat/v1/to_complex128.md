<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.to_complex128" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.to_complex128

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/math_ops.py">View source</a>



Casts a tensor to type `complex128`. (deprecated)

``` python
tf.compat.v1.to_complex128(
    x,
    name='ToComplex128'
)
```



<!-- Placeholder for "Used in" -->

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Use <a href="../../../tf/cast.md"><code>tf.cast</code></a> instead.

#### Args:


* <b>`x`</b>: A `Tensor` or `SparseTensor` or `IndexedSlices`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` or `SparseTensor` or `IndexedSlices` with same shape as `x` with
type `complex128`.



#### Raises:


* <b>`TypeError`</b>: If `x` cannot be cast to the `complex128`.

