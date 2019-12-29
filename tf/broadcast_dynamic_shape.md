<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.broadcast_dynamic_shape" />
<meta itemprop="path" content="Stable" />
</div>

# tf.broadcast_dynamic_shape

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/array_ops.py">View source</a>



Computes the shape of a broadcast given symbolic shapes.

``` python
tf.broadcast_dynamic_shape(
    shape_x,
    shape_y
)
```



<!-- Placeholder for "Used in" -->

When shape_x and shape_y are Tensors representing shapes (i.e. the result of
calling tf.shape on another Tensor) this computes a Tensor which is the shape
of the result of a broadcasting op applied in tensors of shapes shape_x and
shape_y.

For example, if shape_x is [1, 2, 3] and shape_y is [5, 1, 3], the result is a
Tensor whose value is [5, 2, 3].

This is useful when validating the result of a broadcasting operation when the
tensors do not have statically known shapes.

#### Args:


* <b>`shape_x`</b>: A rank 1 integer `Tensor`, representing the shape of x.
* <b>`shape_y`</b>: A rank 1 integer `Tensor`, representing the shape of y.


#### Returns:

A rank 1 integer `Tensor` representing the broadcasted shape.


## Compat aliases

* `tf.compat.v1.broadcast_dynamic_shape`
* `tf.compat.v2.broadcast_dynamic_shape`

