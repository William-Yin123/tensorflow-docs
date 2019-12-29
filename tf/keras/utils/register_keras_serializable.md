<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.utils.register_keras_serializable" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.utils.register_keras_serializable

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/utils/generic_utils.py">View source</a>



Registers an object with the Keras serialization framework.

``` python
tf.keras.utils.register_keras_serializable(
    package='Custom',
    name=None
)
```



<!-- Placeholder for "Used in" -->

This decorator injects the decorated class or function into the Keras custom
object dictionary, so that it can be serialized and deserialized without
needing an entry in the user-provided custom object dict. It also injects a
function that Keras will call to get the object's serializable string key.

Note that to be serialized and deserialized, classes must implement the
`get_config()` method. Functions do not have this requirement.

The object will be registered under the key 'package>name' where `name`,
defaults to the object name if not passed.

#### Arguments:


* <b>`package`</b>: The package that this class belongs to.
* <b>`name`</b>: The name to serialize this class under in this package. If None, the
  class's name will be used.


#### Returns:

A decorator that registers the decorated class with the passed names.


## Compat aliases

* `tf.compat.v1.keras.utils.register_keras_serializable`
* `tf.compat.v2.keras.utils.register_keras_serializable`

