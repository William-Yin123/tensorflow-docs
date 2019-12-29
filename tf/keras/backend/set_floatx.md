<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.set_floatx" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.set_floatx

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend_config.py">View source</a>



Sets the default float type.

``` python
tf.keras.backend.set_floatx(value)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`value`</b>: String; 'float16', 'float32', or 'float64'.
Example: ```python from keras import backend as K K.floatx() >>> 'float32'
  K.set_floatx('float16') K.floatx() >>> 'float16' ```

#### Raises:


* <b>`ValueError`</b>: In case of invalid value.

## Compat aliases

* `tf.compat.v1.keras.backend.set_floatx`
* `tf.compat.v2.keras.backend.set_floatx`

