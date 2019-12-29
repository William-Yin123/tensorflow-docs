<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.is_nan" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.is_nan

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>



Returns which elements of x are NaN.

``` python
tf.math.is_nan(
    x,
    name=None
)
```



<!-- Placeholder for "Used in" -->



#### Example:



```python
x = tf.constant([5.0, np.nan, 6.8, np.nan, np.inf])
tf.math.is_nan(x) ==> [False, True, False, True, False]
```

#### Args:


* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `bool`.


#### Numpy Compatibility
Equivalent to np.isnan



## Compat aliases

* `tf.compat.v1.debugging.is_nan`
* `tf.compat.v1.is_nan`
* `tf.compat.v1.math.is_nan`
* `tf.compat.v2.math.is_nan`

