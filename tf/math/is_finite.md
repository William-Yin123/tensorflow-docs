<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.is_finite" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.is_finite

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>



Returns which elements of x are finite.

``` python
tf.math.is_finite(
    x,
    name=None
)
```



<!-- Placeholder for "Used in" -->



#### Example:



```python
x = tf.constant([5.0, 4.8, 6.8, np.inf, np.nan])
tf.math.is_finite(x) ==> [True, True, True, False, False]
```

#### Args:


* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `bool`.


#### Numpy Compatibility
Equivalent to np.isfinite



## Compat aliases

* `tf.compat.v1.debugging.is_finite`
* `tf.compat.v1.is_finite`
* `tf.compat.v1.math.is_finite`
* `tf.compat.v2.math.is_finite`

