<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.logical_and" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.logical_and

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/math_ops.py">View source</a>



Logical AND function.

**Aliases**: `tf.logical_and`

``` python
tf.math.logical_and(
    x,
    y,
    name=None
)
```



<!-- Placeholder for "Used in" -->

The operation works for the following input types:

- Two single elements of type `bool`
- One <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a> of type `bool` and one single `bool`, where the result will
  be calculated by applying logical AND with the single element to each
  element in the larger Tensor.
- Two <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a> objects of type `bool` of the same shape. In this case,
  the result will be the element-wise logical AND of the two input tensors.

#### Usage:



```
>>> a = tf.constant([True])
>>> b = tf.constant([False])
>>> tf.math.logical_and(a, b)
<tf.Tensor: shape=(1,), dtype=bool, numpy=array([False])>
```

```
>>> c = tf.constant([True])
>>> x = tf.constant([False, True, True, False])
>>> tf.math.logical_and(c, x)
<tf.Tensor: shape=(4,), dtype=bool, numpy=array([False,  True,  True, False])>
```

```
>>> y = tf.constant([False, False, True, True])
>>> z = tf.constant([False, True, False, True])
>>> tf.math.logical_and(y, z)
<tf.Tensor: shape=(4,), dtype=bool, numpy=array([False, False, False,  True])>
```

#### Args:


* <b>`x`</b>: A <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a> type bool.
* <b>`y`</b>: A <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a> of type bool.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a> of type bool with the same size as that of x or y.


## Compat aliases

* `tf.compat.v1.logical_and`
* `tf.compat.v1.math.logical_and`
* `tf.compat.v2.logical_and`
* `tf.compat.v2.math.logical_and`

