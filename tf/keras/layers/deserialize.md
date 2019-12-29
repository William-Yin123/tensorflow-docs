<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.deserialize" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.layers.deserialize

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/serialization.py">View source</a>



Instantiates a layer from a config dictionary.

``` python
tf.keras.layers.deserialize(
    config,
    custom_objects=None
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`config`</b>: dict of the form {'class_name': str, 'config': dict}
* <b>`custom_objects`</b>: dict mapping class names (or function names)
    of custom (non-Keras) objects to class/functions


#### Returns:

Layer instance (may be Model, Sequential, Network, Layer...)


## Compat aliases

* `tf.compat.v1.keras.layers.deserialize`
* `tf.compat.v2.keras.layers.deserialize`

