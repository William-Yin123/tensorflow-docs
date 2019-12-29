<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.models.model_from_yaml" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.models.model_from_yaml

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/saving/model_config.py">View source</a>



Parses a yaml model configuration file and returns a model instance.

``` python
tf.keras.models.model_from_yaml(
    yaml_string,
    custom_objects=None
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`yaml_string`</b>: YAML string encoding a model configuration.
* <b>`custom_objects`</b>: Optional dictionary mapping names
    (strings) to custom classes or functions to be
    considered during deserialization.


#### Returns:

A Keras model instance (uncompiled).



#### Raises:


* <b>`ImportError`</b>: if yaml module is not found.

## Compat aliases

* `tf.compat.v1.keras.models.model_from_yaml`
* `tf.compat.v2.keras.models.model_from_yaml`

