<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.gfile.Copy" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.gfile.Copy

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/lib/io/file_io.py">View source</a>



Copies data from `oldpath` to `newpath`.

``` python
tf.compat.v1.gfile.Copy(
    oldpath,
    newpath,
    overwrite=False
)
```



<!-- Placeholder for "Used in" -->


#### Args:


* <b>`oldpath`</b>: string, name of the file who's contents need to be copied
* <b>`newpath`</b>: string, name of the file to which to copy to
* <b>`overwrite`</b>: boolean, if false it's an error for `newpath` to be occupied by
  an existing file.


#### Raises:


* <b>`errors.OpError`</b>: If the operation fails.

