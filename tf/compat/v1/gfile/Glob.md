<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.gfile.Glob" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.gfile.Glob

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/lib/io/file_io.py">View source</a>



Returns a list of files that match the given pattern(s).

``` python
tf.compat.v1.gfile.Glob(filename)
```



<!-- Placeholder for "Used in" -->


#### Args:


* <b>`filename`</b>: string or iterable of strings. The glob pattern(s).


#### Returns:

A list of strings containing filenames that match the given pattern(s).



#### Raises:


* <b>`errors.OpError`</b>: If there are filesystem / directory listing errors.

