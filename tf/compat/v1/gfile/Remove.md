<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.gfile.Remove" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.gfile.Remove

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/lib/io/file_io.py">View source</a>



Deletes the file located at 'filename'.

``` python
tf.compat.v1.gfile.Remove(filename)
```



<!-- Placeholder for "Used in" -->


#### Args:


* <b>`filename`</b>: string, a filename


#### Raises:


* <b>`errors.OpError`</b>: Propagates any errors reported by the FileSystem API.  E.g.,
`NotFoundError` if the file does not exist.

