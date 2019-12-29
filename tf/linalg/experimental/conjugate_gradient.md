<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.linalg.experimental.conjugate_gradient" />
<meta itemprop="path" content="Stable" />
</div>

# tf.linalg.experimental.conjugate_gradient

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/linalg/sparse/conjugate_gradient.py">View source</a>



Conjugate gradient solver.

``` python
tf.linalg.experimental.conjugate_gradient(
    operator,
    rhs,
    preconditioner=None,
    x=None,
    tol=1e-05,
    max_iter=20,
    name='conjugate_gradient'
)
```



<!-- Placeholder for "Used in" -->

Solves a linear system of equations `A*x = rhs` for self-adjoint, positive
definite matrix `A` and right-hand side vector `rhs`, using an iterative,
matrix-free algorithm where the action of the matrix A is represented by
`operator`. The iteration terminates when either the number of iterations
exceeds `max_iter` or when the residual norm has been reduced to `tol`
times its initial value, i.e. \\(||rhs - A x_k|| <= tol ||rhs||\\).

#### Args:


* <b>`operator`</b>: A `LinearOperator` that is self-adjoint and positive definite.
* <b>`rhs`</b>: A possibly batched vector of shape `[..., N]` containing the right-hand
  size vector.
* <b>`preconditioner`</b>: A `LinearOperator` that approximates the inverse of `A`.
  An efficient preconditioner could dramatically improve the rate of
  convergence. If `preconditioner` represents matrix `M`(`M` approximates
  `A^{-1}`), the algorithm uses `preconditioner.apply(x)` to estimate
  `A^{-1}x`. For this to be useful, the cost of applying `M` should be
  much lower than computing `A^{-1}` directly.
* <b>`x`</b>: A possibly batched vector of shape `[..., N]` containing the initial
  guess for the solution.
* <b>`tol`</b>: A float scalar convergence tolerance.
* <b>`max_iter`</b>: An integer giving the maximum number of iterations.
* <b>`name`</b>: A name scope for the operation.


#### Returns:


* <b>`output`</b>: A namedtuple representing the final state with fields:
  - i: A scalar `int32` `Tensor`. Number of iterations executed.
  - x: A rank-1 `Tensor` of shape `[..., N]` containing the computed
      solution.
  - r: A rank-1 `Tensor` of shape `[.., M]` containing the residual vector.
  - p: A rank-1 `Tensor` of shape `[..., N]`. `A`-conjugate basis vector.
  - gamma: \\(r \dot M \dot r\\), equivalent to  \\(||r||_2^2\\) when
    `preconditioner=None`.

## Compat aliases

* `tf.compat.v1.linalg.experimental.conjugate_gradient`
* `tf.compat.v2.linalg.experimental.conjugate_gradient`

