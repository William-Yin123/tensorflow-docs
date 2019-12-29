<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.dtypes.saturate_cast" />
<meta itemprop="path" content="Stable" />
</div>

# tf.dtypes.saturate_cast

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/math_ops.py">View source</a>



Performs a safe saturating cast of `value` to `dtype`.

**Aliases**: `tf.saturate_cast`

``` python
tf.dtypes.saturate_cast(
    value,
    dtype,
    name=None
)
```



<!-- Placeholder for "Used in" -->

This function casts the input to `dtype` without applying any scaling.  If
there is a danger that values would over or underflow in the cast, this op
applies the appropriate clamping before the cast.

#### Args:


* <b>`value`</b>: A `Tensor`.
* <b>`dtype`</b>: The desired output `DType`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

`value` safely cast to `dtype`.


## Compat aliases

* `tf.compat.v1.dtypes.saturate_cast`
* `tf.compat.v1.saturate_cast`
* `tf.compat.v2.dtypes.saturate_cast`
* `tf.compat.v2.saturate_cast`

