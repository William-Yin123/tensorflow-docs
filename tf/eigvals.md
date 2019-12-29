<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.eigvals" />
<meta itemprop="path" content="Stable" />
</div>

# tf.eigvals

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/linalg_ops.py">View source</a>



Computes the eigenvalues of one or more matrices.

**Aliases**: `tf.linalg.eigvals`

``` python
tf.eigvals(
    tensor,
    name=None
)
```



<!-- Placeholder for "Used in" -->

Note: If your program backpropagates through this function, you should replace
it with a call to tf.linalg.eig (possibly ignoring the second output) to
avoid computing the eigen decomposition twice. This is because the
eigenvectors are used to compute the gradient w.r.t. the eigenvalues. See
_SelfAdjointEigV2Grad in linalg_grad.py.

#### Args:


* <b>`tensor`</b>: `Tensor` of shape `[..., N, N]`.
* <b>`name`</b>: string, optional name of the operation.


#### Returns:


* <b>`e`</b>: Eigenvalues. Shape is `[..., N]`. The vector `e[..., :]` contains the `N`
  eigenvalues of `tensor[..., :, :]`.

## Compat aliases

* `tf.compat.v2.eigvals`
* `tf.compat.v2.linalg.eigvals`

