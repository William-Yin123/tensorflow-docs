<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.einsum" />
<meta itemprop="path" content="Stable" />
</div>

# tf.einsum

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/special_math_ops.py">View source</a>



Tensor contraction over specified indices and outer product.

**Aliases**: `tf.linalg.einsum`

``` python
tf.einsum(
    equation,
    *inputs,
    **kwargs
)
```



<!-- Placeholder for "Used in" -->

Einsum allows defining Tensors by defining their element-wise computation.
This computation is defined by `equation`, a shorthand form based on Einstein
summation. As an example, consider multiplying two matrices A and B to form a
matrix C.  The elements of C are given by:

```
  C[i,k] = sum_j A[i,j] * B[j,k]
```

The corresponding `equation` is:

```
  ij,jk->ik
```

In general, to convert the element-wise equation into the `equation` string,
use the following procedure (intermediate strings for matrix multiplication
example provided in parentheses):

1. remove variable names, brackets, and commas, (`ik = sum_j ij * jk`)
2. replace "*" with ",", (`ik = sum_j ij , jk`)
3. drop summation signs, and (`ik = ij, jk`)
4. move the output to the right, while replacing "=" with "->". (`ij,jk->ik`)

Many common operations can be expressed in this way.  For example:

```python
# Matrix multiplication
einsum('ij,jk->ik', m0, m1)  # output[i,k] = sum_j m0[i,j] * m1[j, k]

# Dot product
einsum('i,i->', u, v)  # output = sum_i u[i]*v[i]

# Outer product
einsum('i,j->ij', u, v)  # output[i,j] = u[i]*v[j]

# Transpose
einsum('ij->ji', m)  # output[j,i] = m[i,j]

# Trace
einsum('ii', m)  # output[j,i] = trace(m) = sum_i m[i, i]

# Batch matrix multiplication
einsum('aij,ajk->aik', s, t)  # out[a,i,k] = sum_j s[a,i,j] * t[a, j, k]
```

To enable and control broadcasting, use an ellipsis.  For example, to perform
batch matrix multiplication with NumPy-style broadcasting across the batch
dimensions, use:

```python
einsum('...ij,...jk->...ik', u, v)
```

#### Args:


* <b>`equation`</b>: a `str` describing the contraction, in the same format as
  `numpy.einsum`.
* <b>`*inputs`</b>: the inputs to contract (each one a `Tensor`), whose shapes should
  be consistent with `equation`.
* <b>`**kwargs`</b>:   - optimize: Optimization strategy to use to find contraction path using
    opt_einsum. Must be 'greedy', 'optimal', 'branch-2', 'branch-all' or
      'auto'. (optional, default: 'greedy').
  - name: A name for the operation (optional).


#### Returns:

The contracted `Tensor`, with shape determined by `equation`.



#### Raises:


* <b>`ValueError`</b>: If
  - the format of `equation` is incorrect,
  - number of inputs or their shapes are inconsistent with `equation`.

## Compat aliases

* `tf.compat.v1.einsum`
* `tf.compat.v1.linalg.einsum`
* `tf.compat.v2.einsum`
* `tf.compat.v2.linalg.einsum`

