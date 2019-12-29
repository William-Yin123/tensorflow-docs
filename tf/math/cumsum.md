<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.cumsum" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.cumsum

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/math_ops.py">View source</a>



Compute the cumulative sum of the tensor `x` along `axis`.

**Aliases**: `tf.cumsum`

``` python
tf.math.cumsum(
    x,
    axis=0,
    exclusive=False,
    reverse=False,
    name=None
)
```



<!-- Placeholder for "Used in" -->

By default, this op performs an inclusive cumsum, which means that the first
element of the input is identical to the first element of the output:
For example:

```
>>> # tf.cumsum([a, b, c])   # [a, a + b, a + b + c]
>>> x = tf.constant([2, 4, 6, 8])
>>> tf.cumsum(x)
<tf.Tensor: shape=(4,), dtype=int32,
numpy=array([ 2,  6, 12, 20], dtype=int32)>
```

```
>>> # using varying `axis` values
>>> y = tf.constant([[2, 4, 6, 8], [1,3,5,7]])
>>> tf.cumsum(y, axis=0)
<tf.Tensor: shape=(2, 4), dtype=int32, numpy=
array([[ 2,  4,  6,  8],
       [ 3,  7, 11, 15]], dtype=int32)>
>>> tf.cumsum(y, axis=1)
<tf.Tensor: shape=(2, 4), dtype=int32, numpy=
array([[ 2,  6, 12, 20],
       [ 1,  4,  9, 16]], dtype=int32)>
```

By setting the `exclusive` kwarg to `True`, an exclusive cumsum is performed
instead:

```
>>> # tf.cumsum([a, b, c], exclusive=True)  => [0, a, a + b]
>>> x = tf.constant([2, 4, 6, 8])
>>> tf.cumsum(x, exclusive=True)
<tf.Tensor: shape=(4,), dtype=int32,
numpy=array([ 0,  2,  6, 12], dtype=int32)>
```

By setting the `reverse` kwarg to `True`, the cumsum is performed in the
opposite direction:

```
>>> # tf.cumsum([a, b, c], reverse=True)  # [a + b + c, b + c, c]
>>> x = tf.constant([2, 4, 6, 8])
>>> tf.cumsum(x, reverse=True)
<tf.Tensor: shape=(4,), dtype=int32,
numpy=array([20, 18, 14,  8], dtype=int32)>
```

This is more efficient than using separate <a href="../../tf/reverse.md"><code>tf.reverse</code></a> ops.
The `reverse` and `exclusive` kwargs can also be combined:

```
>>> # tf.cumsum([a, b, c], exclusive=True, reverse=True)  # [b + c, c, 0]
>>> x = tf.constant([2, 4, 6, 8])
>>> tf.cumsum(x, exclusive=True, reverse=True)
<tf.Tensor: shape=(4,), dtype=int32,
numpy=array([18, 14,  8,  0], dtype=int32)>
```

#### Args:


* <b>`x`</b>: A `Tensor`. Must be one of the following types: `float32`, `float64`,
  `int64`, `int32`, `uint8`, `uint16`, `int16`, `int8`, `complex64`,
  `complex128`, `qint8`, `quint8`, `qint32`, `half`.
* <b>`axis`</b>: A `Tensor` of type `int32` (default: 0). Must be in the range
  `[-rank(x), rank(x))`.
* <b>`exclusive`</b>: If `True`, perform exclusive cumsum.
* <b>`reverse`</b>: A `bool` (default: False).
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.


## Compat aliases

* `tf.compat.v1.cumsum`
* `tf.compat.v1.math.cumsum`
* `tf.compat.v2.cumsum`
* `tf.compat.v2.math.cumsum`

