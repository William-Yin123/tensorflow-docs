<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.resource_loader.get_root_dir_with_all_resources" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.resource_loader.get_root_dir_with_all_resources

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/platform/resource_loader.py">View source</a>



Get a root directory containing all the data attributes in the build rule.

``` python
tf.compat.v1.resource_loader.get_root_dir_with_all_resources()
```



<!-- Placeholder for "Used in" -->


#### Returns:

The path to the specified file present in the data attribute of py_test
or py_binary. Falls back to returning the same as get_data_files_path if it
fails to detect a bazel runfiles directory.


