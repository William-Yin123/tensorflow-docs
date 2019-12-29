<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.gather" />
<meta itemprop="path" content="Stable" />
</div>

# tf.gather

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/array_ops.py">View source</a>



Gather slices from params axis `axis` according to indices.

``` python
tf.gather(
    params,
    indices,
    validate_indices=None,
    axis=None,
    batch_dims=0,
    name=None
)
```



<!-- Placeholder for "Used in" -->

Gather slices from params axis `axis` according to `indices`.  `indices` must
be an integer tensor of any dimension (usually 0-D or 1-D).

For 0-D (scalar) `indices`:

$$\begin{align*}
output[p_0, ..., p_{axis-1}, &&          &&& p_{axis + 1}, ..., p_{N-1}] = \\
params[p_0, ..., p_{axis-1}, && indices, &&& p_{axis + 1}, ..., p_{N-1}]
\end{align*}$$

Where *N* = `ndims(params)`.

For 1-D (vector) `indices` with `batch_dims=0`:

$$\begin{align*}
output[p_0, ..., p_{axis-1}, &&         &i,  &&p_{axis + 1}, ..., p_{N-1}] =\\
params[p_0, ..., p_{axis-1}, && indices[&i], &&p_{axis + 1}, ..., p_{N-1}]
\end{align*}$$

In the general case, produces an output tensor where:

$$\begin{align*}
output[p_0,             &..., p_{axis-1},                       &
       &i_{B},           ..., i_{M-1},                          &
       p_{axis + 1},    &..., p_{N-1}]                          = \\
params[p_0,             &..., p_{axis-1},                       &
       indices[p_0, ..., p_{B-1}, &i_{B}, ..., i_{M-1}],        &
       p_{axis + 1},    &..., p_{N-1}]
\end{align*}$$

Where *N* = `ndims(params)`, *M* = `ndims(indices)`, and *B* = `batch_dims`.
Note that `params.shape[:batch_dims]` must be identical to
`indices.shape[:batch_dims]`.

The shape of the output tensor is:

> `output.shape = params.shape[:axis] + indices.shape[batch_dims:] +
> params.shape[axis + 1:]`.

Note that on CPU, if an out of bound index is found, an error is returned.
On GPU, if an out of bound index is found, a 0 is stored in the corresponding
output value.

See also <a href="../tf/gather_nd.md"><code>tf.gather_nd</code></a>.

<div style="width:70%; margin:auto; margin-bottom:10px; margin-top:20px;">
<img style="width:100%" src="https://www.tensorflow.org/images/Gather.png"
alt>
</div>

#### Args:


* <b>`params`</b>: The `Tensor` from which to gather values. Must be at least rank
  `axis + 1`.
* <b>`indices`</b>: The index `Tensor`.  Must be one of the following types: `int32`,
  `int64`. Must be in range `[0, params.shape[axis])`.
* <b>`validate_indices`</b>: Deprecated, does nothing.
* <b>`axis`</b>: A `Tensor`. Must be one of the following types: `int32`, `int64`. The
  `axis` in `params` to gather `indices` from. Must be greater than or equal
  to `batch_dims`.  Defaults to the first non-batch dimension. Supports
  negative indexes.
* <b>`batch_dims`</b>: An `integer`.  The number of batch dimensions.  Must be less
  than or equal to `rank(indices)`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `params`.


## Compat aliases

* `tf.compat.v2.gather`

