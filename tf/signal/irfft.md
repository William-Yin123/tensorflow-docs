<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.signal.irfft" />
<meta itemprop="path" content="Stable" />
</div>

# tf.signal.irfft

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/signal/fft_ops.py">View source</a>



Inverse real-valued fast Fourier transform.

``` python
tf.signal.irfft(
    input_tensor,
    fft_length=None,
    name=None
)
```



<!-- Placeholder for "Used in" -->

Computes the inverse 1-dimensional discrete Fourier transform of a real-valued
signal over the inner-most dimension of `input`.

The inner-most dimension of `input` is assumed to be the result of `RFFT`: the
`fft_length / 2 + 1` unique components of the DFT of a real-valued signal. If
`fft_length` is not provided, it is computed from the size of the inner-most
dimension of `input` (`fft_length = 2 * (inner - 1)`). If the FFT length used to
compute `input` is odd, it should be provided since it cannot be inferred
properly.

Along the axis `IRFFT` is computed on, if `fft_length / 2 + 1` is smaller
than the corresponding dimension of `input`, the dimension is cropped. If it is
larger, the dimension is padded with zeros.

#### Args:


* <b>`input`</b>: A `Tensor`. Must be one of the following types: `complex64`, `complex128`.
  A complex tensor.
* <b>`fft_length`</b>: A `Tensor` of type `int32`.
  An int32 tensor of shape [1]. The FFT length.
* <b>`Treal`</b>: An optional <a href="../../tf/dtypes/DType.md"><code>tf.DType</code></a> from: `tf.float32, tf.float64`. Defaults to <a href="../../tf.md#float32"><code>tf.float32</code></a>.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `Treal`.


## Compat aliases

* `tf.compat.v1.signal.irfft`
* `tf.compat.v1.spectral.irfft`
* `tf.compat.v2.signal.irfft`

