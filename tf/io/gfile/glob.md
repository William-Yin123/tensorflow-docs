<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.io.gfile.glob" />
<meta itemprop="path" content="Stable" />
</div>

# tf.io.gfile.glob

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/lib/io/file_io.py">View source</a>



Returns a list of files that match the given pattern(s).

``` python
tf.io.gfile.glob(pattern)
```



<!-- Placeholder for "Used in" -->


#### Args:


* <b>`pattern`</b>: string or iterable of strings. The glob pattern(s).


#### Returns:

A list of strings containing filenames that match the given pattern(s).



#### Raises:


* <b>`errors.OpError`</b>: If there are filesystem / directory listing errors.

## Compat aliases

* `tf.compat.v1.io.gfile.glob`
* `tf.compat.v2.io.gfile.glob`

