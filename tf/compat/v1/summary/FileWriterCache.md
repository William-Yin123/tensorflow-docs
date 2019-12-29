<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.summary.FileWriterCache" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="clear"/>
<meta itemprop="property" content="get"/>
</div>

# tf.compat.v1.summary.FileWriterCache

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/summary/writer/writer_cache.py">View source</a>



## Class `FileWriterCache`

Cache for file writers.



<!-- Placeholder for "Used in" -->

This class caches file writers, one per directory.

## Methods

<h3 id="clear"><code>clear</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/summary/writer/writer_cache.py">View source</a>

``` python
@staticmethod
clear()
```

Clear cached summary writers. Currently only used for unit tests.


<h3 id="get"><code>get</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/summary/writer/writer_cache.py">View source</a>

``` python
@staticmethod
get(logdir)
```

Returns the FileWriter for the specified directory.


#### Args:


* <b>`logdir`</b>: str, name of the directory.


#### Returns:

A `FileWriter`.






