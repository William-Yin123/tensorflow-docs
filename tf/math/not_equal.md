<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.not_equal" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.not_equal

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/math_ops.py">View source</a>



Returns the truth value of (x != y) element-wise.

**Aliases**: `tf.not_equal`

``` python
tf.math.not_equal(
    x,
    y,
    name=None
)
```



<!-- Placeholder for "Used in" -->

Performs a [broadcast](
https://docs.scipy.org/doc/numpy/user/basics.broadcasting.html) with the
arguments and then an element-wise inequality comparison, returning a Tensor
of boolean values.

#### For example:



```
>>> x = tf.constant([2, 4])
>>> y = tf.constant(2)
>>> tf.math.not_equal(x, y)
<tf.Tensor: shape=(2,), dtype=bool, numpy=array([False,  True])>
```

```
>>> x = tf.constant([2, 4])
>>> y = tf.constant([2, 4])
>>> tf.math.not_equal(x, y)
<tf.Tensor: shape=(2,), dtype=bool, numpy=array([False,  False])>
```

#### Args:


* <b>`x`</b>: A <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a> or <a href="../../tf/sparse/SparseTensor.md"><code>tf.SparseTensor</code></a> or <a href="../../tf/IndexedSlices.md"><code>tf.IndexedSlices</code></a>.
* <b>`y`</b>: A <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a> or <a href="../../tf/sparse/SparseTensor.md"><code>tf.SparseTensor</code></a> or <a href="../../tf/IndexedSlices.md"><code>tf.IndexedSlices</code></a>.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a> of type bool with the same size as that of x or y.



#### Raises:

<a href="../../tf/errors/InvalidArgumentError.md"><code>tf.errors.InvalidArgumentError</code></a>: If shapes of arguments are incompatible


## Compat aliases

* `tf.compat.v1.math.not_equal`
* `tf.compat.v1.not_equal`
* `tf.compat.v2.math.not_equal`
* `tf.compat.v2.not_equal`

