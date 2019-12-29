<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.preprocessing.image.array_to_img" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.preprocessing.image.array_to_img

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/preprocessing/image.py">View source</a>



Converts a 3D Numpy array to a PIL Image instance.

``` python
tf.keras.preprocessing.image.array_to_img(
    x,
    data_format=None,
    scale=True,
    dtype=None
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`x`</b>: Input Numpy array.
* <b>`data_format`</b>: Image data format.
    either "channels_first" or "channels_last".
* <b>`scale`</b>: Whether to rescale image values
    to be within `[0, 255]`.
* <b>`dtype`</b>: Dtype to use.


#### Returns:

A PIL Image instance.



#### Raises:


* <b>`ImportError`</b>: if PIL is not available.
* <b>`ValueError`</b>: if invalid `x` or `data_format` is passed.

## Compat aliases

* `tf.compat.v1.keras.preprocessing.image.array_to_img`
* `tf.compat.v2.keras.preprocessing.image.array_to_img`

