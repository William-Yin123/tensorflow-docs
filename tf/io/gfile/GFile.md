<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.io.gfile.GFile" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="mode"/>
<meta itemprop="property" content="name"/>
<meta itemprop="property" content="__enter__"/>
<meta itemprop="property" content="__exit__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="__iter__"/>
<meta itemprop="property" content="close"/>
<meta itemprop="property" content="flush"/>
<meta itemprop="property" content="next"/>
<meta itemprop="property" content="read"/>
<meta itemprop="property" content="readline"/>
<meta itemprop="property" content="readlines"/>
<meta itemprop="property" content="seek"/>
<meta itemprop="property" content="seekable"/>
<meta itemprop="property" content="size"/>
<meta itemprop="property" content="tell"/>
<meta itemprop="property" content="write"/>
</div>

# tf.io.gfile.GFile

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/platform/gfile.py">View source</a>



## Class `GFile`

File I/O wrappers without thread locking.



<!-- Placeholder for "Used in" -->

The main roles of the `tf.gfile` module are:

1. To provide an API that is close to Python's file I/O objects, and
2. To provide an implementation based on TensorFlow's C++ FileSystem API.

The C++ FileSystem API supports multiple file system implementations,
including local files, Google Cloud Storage (using a `gs://` prefix, and
HDFS (using an `hdfs://` prefix). TensorFlow exports these as `tf.gfile`,
so that you can use these implementations for saving and loading checkpoints,
writing to TensorBoard logs, and accessing training data (among other uses).
However, if all your files are local, you can use the regular Python file
API without any problem.

*Note*: though similar to Python's I/O implementation, there are semantic
differences to make `tf.gfile` more efficient for backing filesystems. For
example, a write mode file will not be opened until the first write call, to
minimize RPC invocations in network filesystems.

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/platform/gfile.py">View source</a>

``` python
__init__(
    name,
    mode='r'
)
```

Initialize self.  See help(type(self)) for accurate signature.




## Properties

<h3 id="mode"><code>mode</code></h3>

Returns the mode in which the file was opened.


<h3 id="name"><code>name</code></h3>

Returns the file name.




## Methods

<h3 id="__enter__"><code>__enter__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/lib/io/file_io.py">View source</a>

``` python
__enter__()
```

Make usable with "with" statement.


<h3 id="__exit__"><code>__exit__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/lib/io/file_io.py">View source</a>

``` python
__exit__(
    unused_type,
    unused_value,
    unused_traceback
)
```

Make usable with "with" statement.


<h3 id="__iter__"><code>__iter__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/lib/io/file_io.py">View source</a>

``` python
__iter__()
```




<h3 id="close"><code>close</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/lib/io/file_io.py">View source</a>

``` python
close()
```

Closes FileIO. Should be called for the WritableFile to be flushed.


<h3 id="flush"><code>flush</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/lib/io/file_io.py">View source</a>

``` python
flush()
```

Flushes the Writable file.

This only ensures that the data has made its way out of the process without
any guarantees on whether it's written to disk. This means that the
data would survive an application crash but not necessarily an OS crash.

<h3 id="next"><code>next</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/lib/io/file_io.py">View source</a>

``` python
next()
```




<h3 id="read"><code>read</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/lib/io/file_io.py">View source</a>

``` python
read(n=-1)
```

Returns the contents of a file as a string.

Starts reading from current position in file.

#### Args:


* <b>`n`</b>: Read `n` bytes if `n != -1`. If `n = -1`, reads to end of file.


#### Returns:

`n` bytes of the file (or whole file) in bytes mode or `n` bytes of the
string if in string (regular) mode.


<h3 id="readline"><code>readline</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/lib/io/file_io.py">View source</a>

``` python
readline()
```

Reads the next line from the file. Leaves the '\n' at the end.


<h3 id="readlines"><code>readlines</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/lib/io/file_io.py">View source</a>

``` python
readlines()
```

Returns all lines from the file in a list.


<h3 id="seek"><code>seek</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/lib/io/file_io.py">View source</a>

``` python
seek(
    offset=None,
    whence=0,
    position=None
)
```

Seeks to the offset in the file. (deprecated arguments)

Warning: SOME ARGUMENTS ARE DEPRECATED: `(position)`. They will be removed in a future version.
Instructions for updating:
position is deprecated in favor of the offset argument.

#### Args:


* <b>`offset`</b>: The byte count relative to the whence argument.
* <b>`whence`</b>: Valid values for whence are:
  0: start of the file (default)
  1: relative to the current position of the file
  2: relative to the end of file. `offset` is usually negative.

<h3 id="seekable"><code>seekable</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/lib/io/file_io.py">View source</a>

``` python
seekable()
```

Returns True as FileIO supports random access ops of seek()/tell()


<h3 id="size"><code>size</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/lib/io/file_io.py">View source</a>

``` python
size()
```

Returns the size of the file.


<h3 id="tell"><code>tell</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/lib/io/file_io.py">View source</a>

``` python
tell()
```

Returns the current position in the file.


<h3 id="write"><code>write</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/lib/io/file_io.py">View source</a>

``` python
write(file_content)
```

Writes file_content to the file. Appends to the end of the file.






## Compat aliases

* `tf.compat.v1.gfile.GFile`
* `tf.compat.v1.gfile.Open`
* `tf.compat.v1.io.gfile.GFile`
* `tf.compat.v2.io.gfile.GFile`

