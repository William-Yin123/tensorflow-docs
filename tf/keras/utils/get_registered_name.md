<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.utils.get_registered_name" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.utils.get_registered_name

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/utils/generic_utils.py">View source</a>



Returns the name registered to an object within the Keras framework.

``` python
tf.keras.utils.get_registered_name(obj)
```



<!-- Placeholder for "Used in" -->

This function is part of the Keras serialization and deserialization
framework. It maps objects to the string names associated with those objects
for serialization/deserialization.

#### Args:


* <b>`obj`</b>: The object to look up.


#### Returns:

The name associated with the object, or the default Python name if the
  object is not registered.


## Compat aliases

* `tf.compat.v1.keras.utils.get_registered_name`
* `tf.compat.v2.keras.utils.get_registered_name`

