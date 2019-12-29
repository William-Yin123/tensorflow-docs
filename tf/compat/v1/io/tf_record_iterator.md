<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.io.tf_record_iterator" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.io.tf_record_iterator

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/lib/io/tf_record.py">View source</a>



An iterator that read the records from a TFRecords file. (deprecated)

``` python
tf.compat.v1.io.tf_record_iterator(
    path,
    options=None
)
```



<!-- Placeholder for "Used in" -->

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Use eager execution and: 
<a href="../../../../tf/data/TFRecordDataset.md"><code>tf.data.TFRecordDataset(path)</code></a>

#### Args:


* <b>`path`</b>: The path to the TFRecords file.
* <b>`options`</b>: (optional) A TFRecordOptions object.


#### Returns:

An iterator of serialized TFRecords.



#### Raises:


* <b>`IOError`</b>: If `path` cannot be opened for reading.

## Compat aliases

* `tf.compat.v1.python_io.tf_record_iterator`

