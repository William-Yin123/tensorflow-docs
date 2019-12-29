<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.quantization.dequantize" />
<meta itemprop="path" content="Stable" />
</div>

# tf.quantization.dequantize

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/array_ops.py">View source</a>



Dequantize the 'input' tensor into a float Tensor.

``` python
tf.quantization.dequantize(
    input,
    min_range,
    max_range,
    mode='MIN_COMBINED',
    name=None,
    axis=None,
    narrow_range=False
)
```



<!-- Placeholder for "Used in" -->

[min_range, max_range] are scalar floats that specify the range for
the output. The 'mode' attribute controls exactly which calculations are
used to convert the float values to their quantized equivalents.

In 'MIN_COMBINED' mode, each value of the tensor will undergo the following:

```
if T == qint8: in[i] += (range(T) + 1)/ 2.0
out[i] = min_range + (in[i]* (max_range - min_range) / range(T))
```
here `range(T) = numeric_limits<T>::max() - numeric_limits<T>::min()`

*MIN_COMBINED Mode Example*

If the input comes from a QuantizedRelu6, the output type is
quint8 (range of 0-255) but the possible range of QuantizedRelu6 is
0-6.  The min_range and max_range values are therefore 0.0 and 6.0.
Dequantize on quint8 will take each value, cast to float, and multiply
by 6 / 255.
Note that if quantizedtype is qint8, the operation will additionally add
each value by 128 prior to casting.

If the mode is 'MIN_FIRST', then this approach is used:

```c++
num_discrete_values = 1 << (# of bits in T)
range_adjust = num_discrete_values / (num_discrete_values - 1)
range = (range_max - range_min) * range_adjust
range_scale = range / num_discrete_values
const double offset_input = static_cast<double>(input) - lowest_quantized;
result = range_min + ((input - numeric_limits<T>::min()) * range_scale)
```

If the mode is `SCALED`, dequantization is performed by multiplying each
input value by a scaling_factor. (Thus an input of 0 always maps to 0.0).

The scaling_factor is determined from `min_range`, `max_range`, and
`narrow_range` in a way that is compatible with `QuantizeAndDequantize{V2|V3}`
and `QuantizeV2`, using the following algorithm:

```c++

  const int min_expected_T = std::numeric_limits<T>::min() +
    (narrow_range ? 1 : 0);
  const int max_expected_T = std::numeric_limits<T>::max();
  const float max_expected_T = std::numeric_limits<float>::max();

  const float scale_factor =
    (std::numeric_limits<T>::min() == 0) ? (max_range / max_expected_T)
                                         : std::max(min_range / min_expected_T,
                                                    max_range / max_expected_T);
```

#### Args:


* <b>`input`</b>: A `Tensor`. Must be one of the following types: `qint8`, `quint8`, `qint32`, `qint16`, `quint16`.
* <b>`min_range`</b>: A `Tensor` of type `float32`.
  The minimum scalar value possibly produced for the input.
* <b>`max_range`</b>: A `Tensor` of type `float32`.
  The maximum scalar value possibly produced for the input.
* <b>`mode`</b>: An optional `string` from: `"MIN_COMBINED", "MIN_FIRST", "SCALED"`. Defaults to `"MIN_COMBINED"`.
* <b>`narrow_range`</b>: An optional `bool`. Defaults to `False`.
* <b>`axis`</b>: An optional `int`. Defaults to `-1`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `float32`.


## Compat aliases

* `tf.compat.v1.dequantize`
* `tf.compat.v1.quantization.dequantize`
* `tf.compat.v2.quantization.dequantize`

