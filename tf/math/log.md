<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.log" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.log

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>



Computes natural logarithm of x element-wise.

``` python
tf.math.log(
    x,
    name=None
)
```



<!-- Placeholder for "Used in" -->

I.e., \\(y = \log_e x\\).

#### Example:



```python
>>> x = tf.constant([0, 0.5, 1, 5])
>>> tf.math.log(x)
<tf.Tensor: shape=(4,), dtype=float32, numpy=array([      -inf, -0.6931472,  0.       ,  1.609438 ], dtype=float32)>

```

See: https://en.wikipedia.org/wiki/Logarithm

#### Args:


* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`, `complex64`, `complex128`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.


## Compat aliases

* `tf.compat.v1.log`
* `tf.compat.v1.math.log`
* `tf.compat.v2.math.log`

