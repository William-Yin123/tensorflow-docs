<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.signal.fft3d" />
<meta itemprop="path" content="Stable" />
</div>

# tf.signal.fft3d

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>



3D fast Fourier transform.

``` python
tf.signal.fft3d(
    input,
    name=None
)
```



<!-- Placeholder for "Used in" -->

Computes the 3-dimensional discrete Fourier transform over the inner-most 3
dimensions of `input`.

#### Args:


* <b>`input`</b>: A `Tensor`. Must be one of the following types: `complex64`, `complex128`.
  A complex tensor.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `input`.


## Compat aliases

* `tf.compat.v1.fft3d`
* `tf.compat.v1.signal.fft3d`
* `tf.compat.v1.spectral.fft3d`
* `tf.compat.v2.signal.fft3d`

