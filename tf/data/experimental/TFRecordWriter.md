<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.data.experimental.TFRecordWriter" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="write"/>
</div>

# tf.data.experimental.TFRecordWriter

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/data/experimental/ops/writers.py">View source</a>



## Class `TFRecordWriter`

Writes a dataset to a TFRecord file.



<!-- Placeholder for "Used in" -->

The elements of the dataset must be scalar strings. To serialize dataset
elements as strings, you can use the <a href="../../../tf/io/serialize_tensor.md"><code>tf.io.serialize_tensor</code></a> function.

```python
dataset = tf.data.Dataset.range(3)
dataset = dataset.map(tf.io.serialize_tensor)
writer = tf.data.experimental.TFRecordWriter("/path/to/file.tfrecord")
writer.write(dataset)
```

To read back the elements, use `TFRecordDataset`.

```python
dataset = tf.data.TFRecordDataset("/path/to/file.tfrecord")
dataset = dataset.map(lambda x: tf.io.parse_tensor(x, tf.int64))
```

To shard a `dataset` across multiple TFRecord files:

```python
dataset = ... # dataset to be written

def reduce_func(key, dataset):
  filename = tf.strings.join([PATH_PREFIX, tf.strings.as_string(key)])
  writer = tf.data.experimental.TFRecordWriter(filename)
  writer.write(dataset.map(lambda _, x: x))
  return tf.data.Dataset.from_tensors(filename)

dataset = dataset.enumerate()
dataset = dataset.apply(tf.data.experimental.group_by_window(
  lambda i, _: i % NUM_SHARDS, reduce_func, tf.int64.max
))
```

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/data/experimental/ops/writers.py">View source</a>

``` python
__init__(
    filename,
    compression_type=None
)
```

Initializes a `TFRecordWriter`.


#### Args:


* <b>`filename`</b>: a string path indicating where to write the TFRecord data.
* <b>`compression_type`</b>: (Optional.) a string indicating what type of compression
  to use when writing the file. See `tf.io.TFRecordCompressionType` for
  what types of compression are available. Defaults to `None`.



## Methods

<h3 id="write"><code>write</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/data/experimental/ops/writers.py">View source</a>

``` python
write(dataset)
```

Writes a dataset to a TFRecord file.

An operation that writes the content of the specified dataset to the file
specified in the constructor.

If the file exists, it will be overwritten.

#### Args:


* <b>`dataset`</b>: a <a href="../../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a> whose elements are to be written to a file


#### Returns:

In graph mode, this returns an operation which when executed performs the
write. In eager mode, the write is performed by the method itself and
there is no return value.


Raises
  TypeError: if `dataset` is not a <a href="../../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a>.
  TypeError: if the elements produced by the dataset are not scalar strings.





## Compat aliases

* `tf.compat.v1.data.experimental.TFRecordWriter`
* `tf.compat.v2.data.experimental.TFRecordWriter`

