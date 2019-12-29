<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.divide_no_nan" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.divide_no_nan

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/math_ops.py">View source</a>



Computes a safe divide which returns 0 if the y is zero.

``` python
tf.math.divide_no_nan(
    x,
    y,
    name=None
)
```



<!-- Placeholder for "Used in" -->


#### Args:


* <b>`x`</b>: A `Tensor`. Must be one of the following types: `float32`, `float64`.
* <b>`y`</b>: A `Tensor` whose dtype is compatible with `x`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

The element-wise value of the x divided by y.


## Compat aliases

* `tf.compat.v1.div_no_nan`
* `tf.compat.v1.math.divide_no_nan`
* `tf.compat.v2.math.divide_no_nan`

