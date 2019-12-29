<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.less_equal" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.less_equal

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>



Returns the truth value of (x <= y) element-wise.

**Aliases**: `tf.less_equal`

``` python
tf.math.less_equal(
    x,
    y,
    name=None
)
```



<!-- Placeholder for "Used in" -->

*NOTE*: <a href="../../tf/math/less_equal.md"><code>math.less_equal</code></a> supports broadcasting. More about broadcasting
[here](http://docs.scipy.org/doc/numpy/user/basics.broadcasting.html)

#### Example:



```python
x = tf.constant([5, 4, 6])
y = tf.constant([5])
tf.math.less_equal(x, y) ==> [True, True, False]

x = tf.constant([5, 4, 6])
y = tf.constant([5, 6, 6])
tf.math.less_equal(x, y) ==> [True, True, True]
```

#### Args:


* <b>`x`</b>: A `Tensor`. Must be one of the following types: `float32`, `float64`, `int32`, `uint8`, `int16`, `int8`, `int64`, `bfloat16`, `uint16`, `half`, `uint32`, `uint64`.
* <b>`y`</b>: A `Tensor`. Must have the same type as `x`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `bool`.


## Compat aliases

* `tf.compat.v1.less_equal`
* `tf.compat.v1.math.less_equal`
* `tf.compat.v2.less_equal`
* `tf.compat.v2.math.less_equal`

