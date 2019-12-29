<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.utils.get_registered_object" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.utils.get_registered_object

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/utils/generic_utils.py">View source</a>



Returns the class associated with `name` if it is registered with Keras.

``` python
tf.keras.utils.get_registered_object(
    name,
    custom_objects=None,
    module_objects=None
)
```



<!-- Placeholder for "Used in" -->

This function is part of the Keras serialization and deserialization
framework. It maps strings to the objects associated with them for
serialization/deserialization.

#### Example:


```
def from_config(cls, config, custom_objects=None):
  if 'my_custom_object_name' in config:
    config['hidden_cls'] = tf.keras.utils.get_registered_object(
        config['my_custom_object_name'], custom_objects=custom_objects)
```

#### Args:


* <b>`name`</b>: The name to look up.
* <b>`custom_objects`</b>: A dictionary of custom objects to look the name up in.
  Generally, custom_objects is provided by the user.
* <b>`module_objects`</b>: A dictionary of custom objects to look the name up in.
  Generally, module_objects is provided by midlevel library implementers.


#### Returns:

An instantiable class associated with 'name', or None if no such class
  exists.


## Compat aliases

* `tf.compat.v1.keras.utils.get_registered_object`
* `tf.compat.v2.keras.utils.get_registered_object`

