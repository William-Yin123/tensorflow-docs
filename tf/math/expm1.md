<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.expm1" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.expm1

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>



Computes `exp(x) - 1` element-wise.

``` python
tf.math.expm1(
    x,
    name=None
)
```



<!-- Placeholder for "Used in" -->

  i.e. `exp(x) - 1` or `e^(x) - 1`, where `x` is the input tensor.
  `e` denotes Euler's number and is approximately equal to 2.718281.

  ```python
  x = tf.constant(2.0)
  tf.math.expm1(x) ==> 6.389056

  x = tf.constant([2.0, 8.0])
  tf.math.expm1(x) ==> array([6.389056, 2979.958], dtype=float32)

  x = tf.constant(1 + 1j)
  tf.math.expm1(x) ==> (0.46869393991588515+2.2873552871788423j)
  ```

#### Args:


* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`, `complex64`, `complex128`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.


## Compat aliases

* `tf.compat.v1.expm1`
* `tf.compat.v1.math.expm1`
* `tf.compat.v2.math.expm1`

