<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.acosh" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.acosh

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>



Computes inverse hyperbolic cosine of x element-wise.

**Aliases**: `tf.acosh`

``` python
tf.math.acosh(
    x,
    name=None
)
```



<!-- Placeholder for "Used in" -->

Given an input tensor, the function computes inverse hyperbolic cosine of every element.
Input range is `[1, inf]`. It returns `nan` if the input lies outside the range.

```python
x = tf.constant([-2, -0.5, 1, 1.2, 200, 10000, float("inf")])
tf.math.acosh(x) ==> [nan nan 0. 0.62236255 5.9914584 9.903487 inf]
```

#### Args:


* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`, `complex64`, `complex128`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.


## Compat aliases

* `tf.compat.v1.acosh`
* `tf.compat.v1.math.acosh`
* `tf.compat.v2.acosh`
* `tf.compat.v2.math.acosh`

