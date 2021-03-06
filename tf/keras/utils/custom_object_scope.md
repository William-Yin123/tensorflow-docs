<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.utils.custom_object_scope" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.utils.custom_object_scope

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/utils/generic_utils.py">View source</a>



Provides a scope that changes to `_GLOBAL_CUSTOM_OBJECTS` cannot escape.

``` python
tf.keras.utils.custom_object_scope(*args)
```



<!-- Placeholder for "Used in" -->

Convenience wrapper for `CustomObjectScope`.
Code within a `with` statement will be able to access custom objects
by name. Changes to global custom objects persist
within the enclosing `with` statement. At end of the `with` statement,
global custom objects are reverted to state
at beginning of the `with` statement.

#### Example:



Consider a custom object `MyObject`

```python
    with custom_object_scope({'MyObject':MyObject}):
        layer = Dense(..., kernel_regularizer='MyObject')
        # save, load, etc. will recognize custom object by name
```

#### Arguments:


* <b>`*args`</b>: Variable length list of dictionaries of name, class pairs to add to
  custom objects.


#### Returns:

Object of type `CustomObjectScope`.


## Compat aliases

* `tf.compat.v1.keras.utils.custom_object_scope`
* `tf.compat.v2.keras.utils.custom_object_scope`

