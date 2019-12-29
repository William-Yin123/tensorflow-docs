<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.greater" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.greater

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>



Returns the truth value of (x > y) element-wise.

**Aliases**: `tf.greater`

``` python
tf.math.greater(
    x,
    y,
    name=None
)
```



<!-- Placeholder for "Used in" -->

*NOTE*: <a href="../../tf/math/greater.md"><code>math.greater</code></a> supports broadcasting. More about broadcasting
[here](http://docs.scipy.org/doc/numpy/user/basics.broadcasting.html)

#### Example:



```python
x = tf.constant([5, 4, 6])
y = tf.constant([5, 2, 5])
tf.math.greater(x, y) ==> [False, True, True]

x = tf.constant([5, 4, 6])
y = tf.constant([5])
tf.math.greater(x, y) ==> [False, False, True]
```

#### Args:


* <b>`x`</b>: A `Tensor`. Must be one of the following types: `float32`, `float64`, `int32`, `uint8`, `int16`, `int8`, `int64`, `bfloat16`, `uint16`, `half`, `uint32`, `uint64`.
* <b>`y`</b>: A `Tensor`. Must have the same type as `x`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `bool`.


## Compat aliases

* `tf.compat.v1.greater`
* `tf.compat.v1.math.greater`
* `tf.compat.v2.greater`
* `tf.compat.v2.math.greater`

