<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.io.gfile.mkdir" />
<meta itemprop="path" content="Stable" />
</div>

# tf.io.gfile.mkdir

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/lib/io/file_io.py">View source</a>



Creates a directory with the name given by `path`.

``` python
tf.io.gfile.mkdir(path)
```



<!-- Placeholder for "Used in" -->


#### Args:


* <b>`path`</b>: string, name of the directory to be created

Notes: The parent directories need to exist. Use <a href="../../../tf/io/gfile/makedirs.md"><code>tf.io.gfile.makedirs</code></a>
  instead if there is the possibility that the parent dirs don't exist.

#### Raises:


* <b>`errors.OpError`</b>: If the operation fails.

## Compat aliases

* `tf.compat.v1.io.gfile.mkdir`
* `tf.compat.v2.io.gfile.mkdir`

