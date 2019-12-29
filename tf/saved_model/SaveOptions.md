<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.saved_model.SaveOptions" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="namespace_whitelist"/>
<meta itemprop="property" content="save_debug_info"/>
</div>

# tf.saved_model.SaveOptions

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/saved_model/save_options.py">View source</a>



## Class `SaveOptions`

Options for saving to SavedModel.



<!-- Placeholder for "Used in" -->

This function may be used in the `options` argument in functions that
save a SavedModel (<a href="../../tf/saved_model/save.md"><code>tf.saved_model.save</code></a>, <a href="../../tf/keras/models/save_model.md"><code>tf.keras.models.save_model</code></a>).

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/saved_model/save_options.py">View source</a>

``` python
__init__(
    namespace_whitelist=None,
    save_debug_info=False
)
```

Creates an object that stores options for SavedModel saving.


#### Args:


* <b>`namespace_whitelist`</b>: List of strings containing op namespaces to whitelist
  when saving a model. Saving an object that uses namespaced ops must
  explicitly add all namespaces to the whitelist. The namespaced ops must
  be registered into the framework when loading the SavedModel.
* <b>`save_debug_info`</b>: Boolean indicating whether debug information is saved.
  If True, then a debug/saved_model_debug_info.pb file will be written
  with the contents of a GraphDebugInfo binary protocol buffer containing
  stack trace information for all ops and functions that are saved.



## Class Members

* `namespace_whitelist` <a id="namespace_whitelist"></a>
* `save_debug_info` <a id="save_debug_info"></a>


## Compat aliases

* `tf.compat.v1.saved_model.SaveOptions`
* `tf.compat.v2.saved_model.SaveOptions`

