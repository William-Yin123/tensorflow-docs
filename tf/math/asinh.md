<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.asinh" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.asinh

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>



Computes inverse hyperbolic sine of x element-wise.

**Aliases**: `tf.asinh`

``` python
tf.math.asinh(
    x,
    name=None
)
```



<!-- Placeholder for "Used in" -->

  Given an input tensor, this function computes inverse hyperbolic sine
  for every element in the tensor. Both input and output has a range of
  `[-inf, inf]`.

  ```python
  x = tf.constant([-float("inf"), -2, -0.5, 1, 1.2, 200, 10000, float("inf")])
  tf.math.asinh(x) ==> [-inf -1.4436355 -0.4812118 0.8813736 1.0159732 5.991471 9.903487 inf]
  ```

#### Args:


* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`, `complex64`, `complex128`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.


## Compat aliases

* `tf.compat.v1.asinh`
* `tf.compat.v1.math.asinh`
* `tf.compat.v2.asinh`
* `tf.compat.v2.math.asinh`

