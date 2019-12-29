<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.signal.rfft2d" />
<meta itemprop="path" content="Stable" />
</div>

# tf.signal.rfft2d

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/signal/fft_ops.py">View source</a>



2D real-valued fast Fourier transform.

``` python
tf.signal.rfft2d(
    input_tensor,
    fft_length=None,
    name=None
)
```



<!-- Placeholder for "Used in" -->

Computes the 2-dimensional discrete Fourier transform of a real-valued signal
over the inner-most 2 dimensions of `input`.

Since the DFT of a real signal is Hermitian-symmetric, `RFFT2D` only returns the
`fft_length / 2 + 1` unique components of the FFT for the inner-most dimension
of `output`: the zero-frequency term, followed by the `fft_length / 2`
positive-frequency terms.

Along each axis `RFFT2D` is computed on, if `fft_length` is smaller than the
corresponding dimension of `input`, the dimension is cropped. If it is larger,
the dimension is padded with zeros.

#### Args:


* <b>`input`</b>: A `Tensor`. Must be one of the following types: `float32`, `float64`.
  A float32 tensor.
* <b>`fft_length`</b>: A `Tensor` of type `int32`.
  An int32 tensor of shape [2]. The FFT length for each dimension.
* <b>`Tcomplex`</b>: An optional <a href="../../tf/dtypes/DType.md"><code>tf.DType</code></a> from: `tf.complex64, tf.complex128`. Defaults to <a href="../../tf.md#complex64"><code>tf.complex64</code></a>.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `Tcomplex`.


## Compat aliases

* `tf.compat.v1.signal.rfft2d`
* `tf.compat.v1.spectral.rfft2d`
* `tf.compat.v2.signal.rfft2d`

