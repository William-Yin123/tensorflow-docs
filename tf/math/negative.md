<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.negative" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.negative

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>



Computes numerical negative value element-wise.

**Aliases**: `tf.negative`

``` python
tf.math.negative(
    x,
    name=None
)
```



<!-- Placeholder for "Used in" -->

I.e., \\(y = -x\\).

#### Args:


* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`, `int32`, `int64`, `complex64`, `complex128`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.

If `x` is a `SparseTensor`, returns
`SparseTensor(x.indices, tf.math.negative(x.values, ...), x.dense_shape)`


## Compat aliases

* `tf.compat.v1.math.negative`
* `tf.compat.v1.negative`
* `tf.compat.v2.math.negative`
* `tf.compat.v2.negative`

