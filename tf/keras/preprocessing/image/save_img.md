<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.preprocessing.image.save_img" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.preprocessing.image.save_img

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/preprocessing/image.py">View source</a>



Saves an image stored as a Numpy array to a path or file object.

``` python
tf.keras.preprocessing.image.save_img(
    path,
    x,
    data_format=None,
    file_format=None,
    scale=True,
    **kwargs
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`path`</b>: Path or file object.
* <b>`x`</b>: Numpy array.
* <b>`data_format`</b>: Image data format,
    either "channels_first" or "channels_last".
* <b>`file_format`</b>: Optional file format override. If omitted, the
    format to use is determined from the filename extension.
    If a file object was used instead of a filename, this
    parameter should always be used.
* <b>`scale`</b>: Whether to rescale image values to be within `[0, 255]`.
* <b>`**kwargs`</b>: Additional keyword arguments passed to `PIL.Image.save()`.

## Compat aliases

* `tf.compat.v1.keras.preprocessing.image.save_img`
* `tf.compat.v2.keras.preprocessing.image.save_img`

