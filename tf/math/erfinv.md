<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.erfinv" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.erfinv

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/math_ops.py">View source</a>



Compute inverse error function.

``` python
tf.math.erfinv(
    x,
    name=None
)
```



<!-- Placeholder for "Used in" -->

Given `x`, compute the inverse error function of `x`. This function
is the inverse of <a href="../../tf/math/erf.md"><code>tf.math.erf</code></a>.

#### Args:


* <b>`x`</b>: `Tensor` with type `float` or `double`.
* <b>`name`</b>: A name for the operation (optional).

#### Returns:

Inverse error function of `x`.


## Compat aliases

* `tf.compat.v1.math.erfinv`
* `tf.compat.v2.math.erfinv`

