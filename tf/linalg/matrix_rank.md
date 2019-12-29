<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.linalg.matrix_rank" />
<meta itemprop="path" content="Stable" />
</div>

# tf.linalg.matrix_rank

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/linalg/linalg_impl.py">View source</a>



Compute the matrix rank of one or more matrices.

``` python
tf.linalg.matrix_rank(
    a,
    tol=None,
    validate_args=False,
    name=None
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`a`</b>: (Batch of) `float`-like matrix-shaped `Tensor`(s) which are to be
  pseudo-inverted.
* <b>`tol`</b>: Threshold below which the singular value is counted as 'zero'.
  Default value: `None` (i.e., `eps * max(rows, cols) * max(singular_val)`).
* <b>`validate_args`</b>: When `True`, additional assertions might be embedded in the
  graph.
  Default value: `False` (i.e., no graph assertions are added).
* <b>`name`</b>: Python `str` prefixed to ops created by this function.
  Default value: 'matrix_rank'.


#### Returns:


* <b>`matrix_rank`</b>: (Batch of) `int32` scalars representing the number of non-zero
  singular values.

## Compat aliases

* `tf.compat.v1.linalg.matrix_rank`
* `tf.compat.v2.linalg.matrix_rank`

