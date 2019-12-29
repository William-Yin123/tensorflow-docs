<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.scalar_mul" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.scalar_mul

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/math_ops.py">View source</a>



Multiplies a scalar times a `Tensor` or `IndexedSlices` object.

**Aliases**: `tf.scalar_mul`

``` python
tf.math.scalar_mul(
    scalar,
    x,
    name=None
)
```



<!-- Placeholder for "Used in" -->

Intended for use in gradient code which might deal with `IndexedSlices`
objects, which are easy to multiply by a scalar but more expensive to
multiply with arbitrary tensors.

#### Args:


* <b>`scalar`</b>: A 0-D scalar `Tensor`. Must have known shape.
* <b>`x`</b>: A `Tensor` or `IndexedSlices` to be scaled.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

`scalar * x` of the same type (`Tensor` or `IndexedSlices`) as `x`.



#### Raises:


* <b>`ValueError`</b>: if scalar is not a 0-D `scalar`.

## Compat aliases

* `tf.compat.v2.math.scalar_mul`
* `tf.compat.v2.scalar_mul`

