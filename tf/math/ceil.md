<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.ceil" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.ceil

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/math_ops.py">View source</a>



Return the ceiling of the input, element-wise.

``` python
tf.math.ceil(
    x,
    name=None
)
```



<!-- Placeholder for "Used in" -->


#### For example:



```
>>> tf.math.ceil([-1.7, -1.5, -0.2, 0.2, 1.5, 1.7, 2.0])
<tf.Tensor: shape=(7,), dtype=float32,
numpy=array([-1., -1., -0.,  1.,  2.,  2.,  2.], dtype=float32)>
```

#### Args:


* <b>`x`</b>: A <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a>. Must be one of the following types: `bfloat16`, `half`,
  `float32`, `float64`. `int32`
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a>. Has the same type as `x`.




#### Numpy Compatibility
Equivalent to np.ceil



## Compat aliases

* `tf.compat.v1.ceil`
* `tf.compat.v1.math.ceil`
* `tf.compat.v2.math.ceil`

