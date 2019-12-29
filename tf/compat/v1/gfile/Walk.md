<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.gfile.Walk" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.gfile.Walk

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/lib/io/file_io.py">View source</a>



Recursive directory tree generator for directories.

``` python
tf.compat.v1.gfile.Walk(
    top,
    in_order=True
)
```



<!-- Placeholder for "Used in" -->


#### Args:


* <b>`top`</b>: string, a Directory name
* <b>`in_order`</b>: bool, Traverse in order if True, post order if False.  Errors that
  happen while listing directories are ignored.


#### Yields:

Each yield is a 3-tuple:  the pathname of a directory, followed by lists of
all its subdirectories and leaf files. That is, each yield looks like:
`(dirname, [subdirname, subdirname, ...], [filename, filename, ...])`.
Each item is a string.


