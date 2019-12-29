<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.io.TFRecordWriter" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="__new__"/>
<meta itemprop="property" content="close"/>
<meta itemprop="property" content="flush"/>
<meta itemprop="property" content="write"/>
</div>

# tf.io.TFRecordWriter

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/lib/io/tf_record.py">View source</a>



## Class `TFRecordWriter`

A class to write records to a TFRecords file.



<!-- Placeholder for "Used in" -->

[TFRecords tutorial](https://www.tensorflow.org/tutorials/load_data/tfrecord)

TFRecords is a binary format which is optimized for high throughput data
retrieval, generally in conjunction with <a href="../../tf/data.md"><code>tf.data</code></a>. `TFRecordWriter` is used
to write serialized examples to a file for later consumption. The key steps
are:

 Ahead of time:

 - [Convert data into a serialized format](
 https://www.tensorflow.org/tutorials/load_data/tfrecord#tfexample)
 - [Write the serialized data to one or more files](
 https://www.tensorflow.org/tutorials/load_data/tfrecord#tfrecord_files_in_python)

 During training or evaluation:

 - [Read serialized examples into memory](
 https://www.tensorflow.org/tutorials/load_data/tfrecord#reading_a_tfrecord_file)
 - [Parse (deserialize) examples](
 https://www.tensorflow.org/tutorials/load_data/tfrecord#reading_a_tfrecord_file)

A minimal example is given below:

```
>>> import tempfile
>>> example_path = os.path.join(tempfile.gettempdir(), "example.tfrecords")
>>> np.random.seed(0)
```

```
>>> # Write the records to a file.
... with tf.io.TFRecordWriter(example_path) as file_writer:
...   for _ in range(4):
...     x, y = np.random.random(), np.random.random()
...
...     record_bytes = tf.train.Example(features=tf.train.Features(feature={
...         "x": tf.train.Feature(float_list=tf.train.FloatList(value=[x])),
...         "y": tf.train.Feature(float_list=tf.train.FloatList(value=[y])),
...     })).SerializeToString()
...     file_writer.write(record_bytes)
```

```
>>> # Read the data back out.
>>> def decode_fn(record_bytes):
...   return tf.io.parse_single_example(
...       # Data
...       record_bytes,
...
...       # Schema
...       {"x": tf.io.FixedLenFeature([], dtype=tf.float32),
...        "y": tf.io.FixedLenFeature([], dtype=tf.float32)}
...   )
```

```
>>> for batch in tf.data.TFRecordDataset([example_path]).map(decode_fn):
...   print("x = {x:.4f},  y = {y:.4f}".format(**batch))
x = 0.5488,  y = 0.7152
x = 0.6028,  y = 0.5449
x = 0.4237,  y = 0.6459
x = 0.4376,  y = 0.8918
```

This class implements `__enter__` and `__exit__`, and can be used
in `with` blocks like a normal file. (See the usage example above.)

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/lib/io/tf_record.py">View source</a>

``` python
__init__(
    path,
    options=None
)
```

Opens file `path` and creates a `TFRecordWriter` writing to it.


#### Args:


* <b>`path`</b>: The path to the TFRecords file.
* <b>`options`</b>: (optional) String specifying compression type,
    `TFRecordCompressionType`, or `TFRecordOptions` object.


#### Raises:


* <b>`IOError`</b>: If `path` cannot be opened for writing.
* <b>`ValueError`</b>: If valid compression_type can't be determined from `options`.

<h2 id="__new__"><code>__new__</code></h2>

``` python
__new__(
    type,
    *args,
    **kwargs
)
```






## Methods

<h3 id="close"><code>close</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/lib/io/tf_record.py">View source</a>

``` python
close()
```

Close the file.


<h3 id="flush"><code>flush</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/lib/io/tf_record.py">View source</a>

``` python
flush()
```

Flush the file.


<h3 id="write"><code>write</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/lib/io/tf_record.py">View source</a>

``` python
write(record)
```

Write a string record to the file.


#### Args:


* <b>`record`</b>: str





## Compat aliases

* `tf.compat.v1.io.TFRecordWriter`
* `tf.compat.v1.python_io.TFRecordWriter`
* `tf.compat.v2.io.TFRecordWriter`

