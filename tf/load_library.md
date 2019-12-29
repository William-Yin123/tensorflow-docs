<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.load_library" />
<meta itemprop="path" content="Stable" />
</div>

# tf.load_library

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/framework/load_library.py">View source</a>



Loads a TensorFlow plugin.

``` python
tf.load_library(library_location)
```



<!-- Placeholder for "Used in" -->

"library_location" can be a path to a specific shared object, or a folder.
If it is a folder, all shared objects that are named "libtfkernel*" will be
loaded. When the library is loaded, kernels registered in the library via the
`REGISTER_*` macros are made available in the TensorFlow process.

#### Args:


* <b>`library_location`</b>: Path to the plugin or the folder of plugins.
  Relative or absolute filesystem path to a dynamic library file or folder.


#### Returns:

None



#### Raises:


* <b>`OSError`</b>: When the file to be loaded is not found.
* <b>`RuntimeError`</b>: when unable to load the library.

## Compat aliases

* `tf.compat.v1.load_library`
* `tf.compat.v2.load_library`

