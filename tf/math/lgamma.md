<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.lgamma" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.lgamma

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>



Computes the log of the absolute value of `Gamma(x)` element-wise.

``` python
tf.math.lgamma(
    x,
    name=None
)
```



<!-- Placeholder for "Used in" -->

  For positive numbers, this function computes log((input - 1)!) for every element in the tensor.
  `lgamma(5) = log((5-1)!) = log(4!) = log(24) = 3.1780539`

#### Example:



```python
x = tf.constant([0, 0.5, 1, 4.5, -4, -5.6])
tf.math.lgamma(x) ==> [inf, 0.5723649, 0., 2.4537368, inf, -4.6477685]
```

#### Args:


* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.


## Compat aliases

* `tf.compat.v1.lgamma`
* `tf.compat.v1.math.lgamma`
* `tf.compat.v2.math.lgamma`

