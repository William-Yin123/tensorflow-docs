<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.signal.fft" />
<meta itemprop="path" content="Stable" />
</div>

# tf.signal.fft

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>



Fast Fourier transform.

``` python
tf.signal.fft(
    input,
    name=None
)
```



<!-- Placeholder for "Used in" -->

Computes the 1-dimensional discrete Fourier transform over the inner-most
dimension of `input`.

#### Args:


* <b>`input`</b>: A `Tensor`. Must be one of the following types: `complex64`, `complex128`.
  A complex tensor.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `input`.


## Compat aliases

* `tf.compat.v1.fft`
* `tf.compat.v1.signal.fft`
* `tf.compat.v1.spectral.fft`
* `tf.compat.v2.signal.fft`

