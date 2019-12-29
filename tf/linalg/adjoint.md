<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.linalg.adjoint" />
<meta itemprop="path" content="Stable" />
</div>

# tf.linalg.adjoint

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/linalg/linalg_impl.py">View source</a>



Transposes the last two dimensions of and conjugates tensor `matrix`.

``` python
tf.linalg.adjoint(
    matrix,
    name=None
)
```



<!-- Placeholder for "Used in" -->


#### For example:



```python
x = tf.constant([[1 + 1j, 2 + 2j, 3 + 3j],
                 [4 + 4j, 5 + 5j, 6 + 6j]])
tf.linalg.adjoint(x)  # [[1 - 1j, 4 - 4j],
                      #  [2 - 2j, 5 - 5j],
                      #  [3 - 3j, 6 - 6j]]
```

#### Args:


* <b>`matrix`</b>:  A `Tensor`. Must be `float16`, `float32`, `float64`, `complex64`,
  or `complex128` with shape `[..., M, M]`.
* <b>`name`</b>:  A name to give this `Op` (optional).


#### Returns:

The adjoint (a.k.a. Hermitian transpose a.k.a. conjugate transpose) of
matrix.


## Compat aliases

* `tf.compat.v1.linalg.adjoint`
* `tf.compat.v2.linalg.adjoint`

