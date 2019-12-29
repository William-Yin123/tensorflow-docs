<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.preprocessing.image.apply_brightness_shift" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.preprocessing.image.apply_brightness_shift

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>



Performs a brightness shift.

``` python
tf.keras.preprocessing.image.apply_brightness_shift(
    x,
    brightness
)
```



<!-- Placeholder for "Used in" -->

# Arguments
    x: Input tensor. Must be 3D.
    brightness: Float. The new brightness value.
    channel_axis: Index of axis for channels in the input tensor.

# Returns
    Numpy image tensor.

# Raises
    ValueError if `brightness_range` isn't a tuple.

## Compat aliases

* `tf.compat.v1.keras.preprocessing.image.apply_brightness_shift`
* `tf.compat.v2.keras.preprocessing.image.apply_brightness_shift`

