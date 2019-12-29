<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.io.gfile.exists" />
<meta itemprop="path" content="Stable" />
</div>

# tf.io.gfile.exists

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/lib/io/file_io.py">View source</a>



Determines whether a path exists or not.

``` python
tf.io.gfile.exists(path)
```



<!-- Placeholder for "Used in" -->


#### Args:


* <b>`path`</b>: string, a path


#### Returns:

True if the path exists, whether it's a file or a directory.
False if the path does not exist and there are no filesystem errors.



#### Raises:


* <b>`errors.OpError`</b>: Propagates any errors reported by the FileSystem API.

## Compat aliases

* `tf.compat.v1.io.gfile.exists`
* `tf.compat.v2.io.gfile.exists`

