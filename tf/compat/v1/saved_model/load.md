<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.saved_model.load" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.saved_model.load

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/saved_model/loader_impl.py">View source</a>



Loads the model from a SavedModel as specified by tags. (deprecated)

``` python
tf.compat.v1.saved_model.load(
    sess,
    tags,
    export_dir,
    import_scope=None,
    **saver_kwargs
)
```



<!-- Placeholder for "Used in" -->

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
This function will only be available through the v1 compatibility library as tf.compat.v1.saved_model.loader.load or tf.compat.v1.saved_model.load. There will be a new function for importing SavedModels in Tensorflow 2.0.

#### Args:


* <b>`sess`</b>: The TensorFlow session to restore the variables.
* <b>`tags`</b>: Set of string tags to identify the required MetaGraphDef. These should
    correspond to the tags used when saving the variables using the
    SavedModel `save()` API.
* <b>`export_dir`</b>: Directory in which the SavedModel protocol buffer and variables
    to be loaded are located.
* <b>`import_scope`</b>: Optional `string` -- if specified, prepend this string
    followed by '/' to all loaded tensor names. This scope is applied to
    tensor instances loaded into the passed session, but it is *not* written
    through to the static `MetaGraphDef` protocol buffer that is returned.
* <b>`**saver_kwargs`</b>: Optional keyword arguments passed through to Saver.


#### Returns:

The `MetaGraphDef` protocol buffer loaded in the provided session. This
can be used to further extract signature-defs, collection-defs, etc.



#### Raises:


* <b>`RuntimeError`</b>: MetaGraphDef associated with the tags cannot be found.

## Compat aliases

* `tf.compat.v1.saved_model.loader.load`

