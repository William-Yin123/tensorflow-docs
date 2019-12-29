<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.logical_xor" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.logical_xor

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/math_ops.py">View source</a>



Logical XOR function.

``` python
tf.math.logical_xor(
    x,
    y,
    name='LogicalXor'
)
```



<!-- Placeholder for "Used in" -->

x ^ y = (x | y) & ~(x & y)

The operation works for the following input types:

- Two single elements of type `bool`
- One <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a> of type `bool` and one single `bool`, where the result will
  be calculated by applying logical XOR with the single element to each
  element in the larger Tensor.
- Two <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a> objects of type `bool` of the same shape. In this case,
  the result will be the element-wise logical XOR of the two input tensors.

#### Usage:



```
>>> a = tf.constant([True])
>>> b = tf.constant([False])
>>> tf.math.logical_xor(a, b)
<tf.Tensor: shape=(1,), dtype=bool, numpy=array([ True])>
```

```
>>> c = tf.constant([True])
>>> x = tf.constant([False, True, True, False])
>>> tf.math.logical_xor(c, x)
<tf.Tensor: shape=(4,), dtype=bool, numpy=array([ True, False, False,  True])>
```

```
>>> y = tf.constant([False, False, True, True])
>>> z = tf.constant([False, True, False, True])
>>> tf.math.logical_xor(y, z)
<tf.Tensor: shape=(4,), dtype=bool, numpy=array([False,  True,  True, False])>
```

#### Args:


* <b>`x`</b>: A <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a> type bool.
* <b>`y`</b>: A <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a> of type bool.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a> of type bool with the same size as that of x or y.


## Compat aliases

* `tf.compat.v1.logical_xor`
* `tf.compat.v1.math.logical_xor`
* `tf.compat.v2.math.logical_xor`

