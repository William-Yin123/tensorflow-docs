<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.quantization.fake_quant_with_min_max_args_gradient" />
<meta itemprop="path" content="Stable" />
</div>

# tf.quantization.fake_quant_with_min_max_args_gradient

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>



Compute gradients for a FakeQuantWithMinMaxArgs operation.

``` python
tf.quantization.fake_quant_with_min_max_args_gradient(
    gradients,
    inputs,
    min=-6,
    max=6,
    num_bits=8,
    narrow_range=False,
    name=None
)
```



<!-- Placeholder for "Used in" -->


#### Args:


* <b>`gradients`</b>: A `Tensor` of type `float32`.
  Backpropagated gradients above the FakeQuantWithMinMaxArgs operation.
* <b>`inputs`</b>: A `Tensor` of type `float32`.
  Values passed as inputs to the FakeQuantWithMinMaxArgs operation.
* <b>`min`</b>: An optional `float`. Defaults to `-6`.
* <b>`max`</b>: An optional `float`. Defaults to `6`.
* <b>`num_bits`</b>: An optional `int`. Defaults to `8`.
* <b>`narrow_range`</b>: An optional `bool`. Defaults to `False`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `float32`.


## Compat aliases

* `tf.compat.v1.fake_quant_with_min_max_args_gradient`
* `tf.compat.v1.quantization.fake_quant_with_min_max_args_gradient`
* `tf.compat.v2.quantization.fake_quant_with_min_max_args_gradient`

