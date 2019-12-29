<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.preprocessing.image.img_to_array" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.preprocessing.image.img_to_array

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/preprocessing/image.py">View source</a>



Converts a PIL Image instance to a Numpy array.

``` python
tf.keras.preprocessing.image.img_to_array(
    img,
    data_format=None,
    dtype=None
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`img`</b>: PIL Image instance.
* <b>`data_format`</b>: Image data format,
    either "channels_first" or "channels_last".
* <b>`dtype`</b>: Dtype to use for the returned array.


#### Returns:

A 3D Numpy array.



#### Raises:


* <b>`ValueError`</b>: if invalid `img` or `data_format` is passed.

## Compat aliases

* `tf.compat.v1.keras.preprocessing.image.img_to_array`
* `tf.compat.v2.keras.preprocessing.image.img_to_array`

