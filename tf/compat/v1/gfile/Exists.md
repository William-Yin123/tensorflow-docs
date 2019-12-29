<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.gfile.Exists" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.gfile.Exists

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/lib/io/file_io.py">View source</a>



Determines whether a path exists or not.

``` python
tf.compat.v1.gfile.Exists(filename)
```



<!-- Placeholder for "Used in" -->


#### Args:


* <b>`filename`</b>: string, a path


#### Returns:

True if the path exists, whether it's a file or a directory.
False if the path does not exist and there are no filesystem errors.



#### Raises:


* <b>`errors.OpError`</b>: Propagates any errors reported by the FileSystem API.

