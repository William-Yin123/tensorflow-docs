<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.set_image_data_format" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.set_image_data_format

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend_config.py">View source</a>



Sets the value of the image data format convention.

``` python
tf.keras.backend.set_image_data_format(data_format)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`data_format`</b>: string. `'channels_first'` or `'channels_last'`.
Example: ```python from keras import backend as K K.image_data_format() >>>
  'channels_first' K.set_image_data_format('channels_last')
  K.image_data_format() >>> 'channels_last' ```

#### Raises:


* <b>`ValueError`</b>: In case of invalid `data_format` value.

## Compat aliases

* `tf.compat.v1.keras.backend.set_image_data_format`
* `tf.compat.v2.keras.backend.set_image_data_format`

