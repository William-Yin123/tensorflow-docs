<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.preprocessing.image.random_brightness" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.preprocessing.image.random_brightness

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>



Performs a random brightness shift.

``` python
tf.keras.preprocessing.image.random_brightness(
    x,
    brightness_range
)
```



<!-- Placeholder for "Used in" -->

# Arguments
    x: Input tensor. Must be 3D.
    brightness_range: Tuple of floats; brightness range.
    channel_axis: Index of axis for channels in the input tensor.

# Returns
    Numpy image tensor.

# Raises
    ValueError if `brightness_range` isn't a tuple.

## Compat aliases

* `tf.compat.v1.keras.preprocessing.image.random_brightness`
* `tf.compat.v2.keras.preprocessing.image.random_brightness`

