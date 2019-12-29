<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.rint" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.rint

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>



Returns element-wise integer closest to x.

``` python
tf.math.rint(
    x,
    name=None
)
```



<!-- Placeholder for "Used in" -->

If the result is midway between two representable values,
the even representable is chosen.
For example:

```
rint(-1.5) ==> -2.0
rint(0.5000001) ==> 1.0
rint([-1.7, -1.5, -0.2, 0.2, 1.5, 1.7, 2.0]) ==> [-2., -2., -0., 0., 2., 2., 2.]
```

#### Args:


* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.


## Compat aliases

* `tf.compat.v1.math.rint`
* `tf.compat.v1.rint`
* `tf.compat.v2.math.rint`

