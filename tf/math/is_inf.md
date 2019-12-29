<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.is_inf" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.is_inf

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>



Returns which elements of x are Inf.

``` python
tf.math.is_inf(
    x,
    name=None
)
```



<!-- Placeholder for "Used in" -->



#### Example:



```python
x = tf.constant([5.0, np.inf, 6.8, np.inf])
tf.math.is_inf(x) ==> [False, True, False, True]
```

#### Args:


* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `bool`.


#### Numpy Compatibility
Equivalent to np.isinf



## Compat aliases

* `tf.compat.v1.debugging.is_inf`
* `tf.compat.v1.is_inf`
* `tf.compat.v1.math.is_inf`
* `tf.compat.v2.math.is_inf`

