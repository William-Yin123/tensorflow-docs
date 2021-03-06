<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.saved_model.Asset" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="asset_path"/>
<meta itemprop="property" content="__init__"/>
</div>

# tf.saved_model.Asset

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/training/tracking/tracking.py">View source</a>



## Class `Asset`

Represents a file asset to hermetically include in a SavedModel.



<!-- Placeholder for "Used in" -->

A SavedModel can include arbitrary files, called assets, that are needed
for its use. For example a vocabulary file used initialize a lookup table.

When a trackable object is exported via <a href="../../tf/saved_model/save.md"><code>tf.saved_model.save()</code></a>, all the
`Asset`s reachable from it are copied into the SavedModel assets directory.
Upon loading, the assets and the serialized functions that depend on them
will refer to the correct filepaths inside the SavedModel directory.

#### Example:



```
filename = tf.saved_model.Asset("file.txt")

@tf.function(input_signature=[])
def func():
  return tf.io.read_file(filename)

trackable_obj = tf.train.Checkpoint()
trackable_obj.func = func
trackable_obj.filename = filename
tf.saved_model.save(trackable_obj, "/tmp/saved_model")

# The created SavedModel is hermetic, it does not depend on
# the original file and can be moved to another path.
tf.io.gfile.remove("file.txt")
tf.io.gfile.rename("/tmp/saved_model", "/tmp/new_location")

reloaded_obj = tf.saved_model.load("/tmp/new_location")
print(reloaded_obj.func())
```

#### Attributes:


* <b>`asset_path`</b>: A 0-D <a href="../../tf.md#string"><code>tf.string</code></a> tensor with path to the asset.

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/training/tracking/tracking.py">View source</a>

``` python
__init__(path)
```

Record the full path to the asset.




## Properties

<h3 id="asset_path"><code>asset_path</code></h3>

Fetch the current asset path.






## Compat aliases

* `tf.compat.v1.saved_model.Asset`
* `tf.compat.v2.saved_model.Asset`

