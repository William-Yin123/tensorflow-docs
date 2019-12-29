<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.eig" />
<meta itemprop="path" content="Stable" />
</div>

# tf.eig

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/linalg_ops.py">View source</a>



Computes the eigen decomposition of a batch of matrices.

**Aliases**: `tf.linalg.eig`

``` python
tf.eig(
    tensor,
    name=None
)
```



<!-- Placeholder for "Used in" -->

The eigenvalues
and eigenvectors for a non-Hermitian matrix in general are complex. The
eigenvectors are not guaranteed to be linearly independent.

Computes the eigenvalues and right eigenvectors of the innermost
N-by-N matrices in `tensor` such that
`tensor[...,:,:] * v[..., :,i] = e[..., i] * v[...,:,i]`, for i=0...N-1.

#### Args:


* <b>`tensor`</b>: `Tensor` of shape `[..., N, N]`. Only the lower triangular part of
  each inner inner matrix is referenced.
* <b>`name`</b>: string, optional name of the operation.


#### Returns:


* <b>`e`</b>: Eigenvalues. Shape is `[..., N]`. Sorted in non-decreasing order.
* <b>`v`</b>: Eigenvectors. Shape is `[..., N, N]`. The columns of the inner most
  matrices contain eigenvectors of the corresponding matrices in `tensor`

## Compat aliases

* `tf.compat.v2.eig`
* `tf.compat.v2.linalg.eig`

