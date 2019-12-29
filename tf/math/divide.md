<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.divide" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.divide

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/math_ops.py">View source</a>



Computes Python style division of `x` by `y`.

**Aliases**: `tf.divide`

``` python
tf.math.divide(
    x,
    y,
    name=None
)
```



<!-- Placeholder for "Used in" -->


#### For example:



```
>>> x = tf.constant([16, 12, 11])
>>> y = tf.constant([4, 6, 2])
>>> tf.divide(x,y)
<tf.Tensor: shape=(3,), dtype=float64,
numpy=array([4. , 2. , 5.5])>
```

#### Args:


* <b>`x`</b>: A `Tensor`
* <b>`y`</b>: A `Tensor`
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` with same shape as input


## Compat aliases

* `tf.compat.v1.divide`
* `tf.compat.v1.math.divide`
* `tf.compat.v2.divide`
* `tf.compat.v2.math.divide`

