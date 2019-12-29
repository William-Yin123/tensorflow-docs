<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.linalg.logdet" />
<meta itemprop="path" content="Stable" />
</div>

# tf.linalg.logdet

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/linalg/linalg_impl.py">View source</a>



Computes log of the determinant of a hermitian positive definite matrix.

``` python
tf.linalg.logdet(
    matrix,
    name=None
)
```



<!-- Placeholder for "Used in" -->

```python
# Compute the determinant of a matrix while reducing the chance of over- or
underflow:
A = ... # shape 10 x 10
det = tf.exp(tf.linalg.logdet(A))  # scalar
```

#### Args:


* <b>`matrix`</b>:  A `Tensor`. Must be `float16`, `float32`, `float64`, `complex64`,
  or `complex128` with shape `[..., M, M]`.
* <b>`name`</b>:  A name to give this `Op`.  Defaults to `logdet`.


#### Returns:

The natural log of the determinant of `matrix`.




#### Numpy Compatibility
Equivalent to numpy.linalg.slogdet, although no sign is returned since only
hermitian positive definite matrices are supported.



## Compat aliases

* `tf.compat.v1.linalg.logdet`
* `tf.compat.v2.linalg.logdet`

