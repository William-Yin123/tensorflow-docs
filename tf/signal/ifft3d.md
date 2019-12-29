<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.signal.ifft3d" />
<meta itemprop="path" content="Stable" />
</div>

# tf.signal.ifft3d

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>



Inverse 3D fast Fourier transform.

``` python
tf.signal.ifft3d(
    input,
    name=None
)
```



<!-- Placeholder for "Used in" -->

Computes the inverse 3-dimensional discrete Fourier transform over the
inner-most 3 dimensions of `input`.

#### Args:


* <b>`input`</b>: A `Tensor`. Must be one of the following types: `complex64`, `complex128`.
  A complex tensor.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `input`.


## Compat aliases

* `tf.compat.v1.ifft3d`
* `tf.compat.v1.signal.ifft3d`
* `tf.compat.v1.spectral.ifft3d`
* `tf.compat.v2.signal.ifft3d`

