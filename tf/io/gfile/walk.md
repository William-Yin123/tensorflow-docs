<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.io.gfile.walk" />
<meta itemprop="path" content="Stable" />
</div>

# tf.io.gfile.walk

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/lib/io/file_io.py">View source</a>



Recursive directory tree generator for directories.

``` python
tf.io.gfile.walk(
    top,
    topdown=True,
    onerror=None
)
```



<!-- Placeholder for "Used in" -->


#### Args:


* <b>`top`</b>: string, a Directory name
* <b>`topdown`</b>: bool, Traverse pre order if True, post order if False.
* <b>`onerror`</b>: optional handler for errors. Should be a function, it will be
  called with the error as argument. Rethrowing the error aborts the walk.
  Errors that happen while listing directories are ignored.


#### Yields:

Each yield is a 3-tuple:  the pathname of a directory, followed by lists of
all its subdirectories and leaf files. That is, each yield looks like:
`(dirname, [subdirname, subdirname, ...], [filename, filename, ...])`.
Each item is a string.


## Compat aliases

* `tf.compat.v1.io.gfile.walk`
* `tf.compat.v2.io.gfile.walk`

