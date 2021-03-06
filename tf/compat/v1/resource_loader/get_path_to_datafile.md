<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.resource_loader.get_path_to_datafile" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.resource_loader.get_path_to_datafile

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/platform/resource_loader.py">View source</a>



Get the path to the specified file in the data dependencies.

``` python
tf.compat.v1.resource_loader.get_path_to_datafile(path)
```



<!-- Placeholder for "Used in" -->

The path is relative to tensorflow/

#### Args:


* <b>`path`</b>: a string resource path relative to tensorflow/


#### Returns:

The path to the specified file present in the data attribute of py_test
or py_binary.



#### Raises:


* <b>`IOError`</b>: If the path is not found, or the resource can't be opened.

