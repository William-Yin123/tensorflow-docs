<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.minimum" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.minimum

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>



Returns the min of x and y (i.e. x < y ? x : y) element-wise.

**Aliases**: `tf.minimum`

``` python
tf.math.minimum(
    x,
    y,
    name=None
)
```



<!-- Placeholder for "Used in" -->


#### Example:


>>> x = tf.constant([0., 0., 0., 0.])
>>> y = tf.constant([-5., -2., 0., 3.])
>>> tf.math.minimum(x, y)
<tf.Tensor: shape=(4,), dtype=float32, numpy=array([-5., -2., 0., 0.], dtype=float32)>

#### Args:


* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`, `int32`, `int64`.
* <b>`y`</b>: A `Tensor`. Must have the same type as `x`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.


## Compat aliases

* `tf.compat.v1.math.minimum`
* `tf.compat.v1.minimum`
* `tf.compat.v2.math.minimum`
* `tf.compat.v2.minimum`

