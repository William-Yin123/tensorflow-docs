<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.data.TFRecordDataset" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="element_spec"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="__iter__"/>
<meta itemprop="property" content="apply"/>
<meta itemprop="property" content="as_numpy_iterator"/>
<meta itemprop="property" content="batch"/>
<meta itemprop="property" content="cache"/>
<meta itemprop="property" content="concatenate"/>
<meta itemprop="property" content="enumerate"/>
<meta itemprop="property" content="filter"/>
<meta itemprop="property" content="flat_map"/>
<meta itemprop="property" content="from_generator"/>
<meta itemprop="property" content="from_tensor_slices"/>
<meta itemprop="property" content="from_tensors"/>
<meta itemprop="property" content="interleave"/>
<meta itemprop="property" content="list_files"/>
<meta itemprop="property" content="map"/>
<meta itemprop="property" content="options"/>
<meta itemprop="property" content="padded_batch"/>
<meta itemprop="property" content="prefetch"/>
<meta itemprop="property" content="range"/>
<meta itemprop="property" content="reduce"/>
<meta itemprop="property" content="repeat"/>
<meta itemprop="property" content="shard"/>
<meta itemprop="property" content="shuffle"/>
<meta itemprop="property" content="skip"/>
<meta itemprop="property" content="take"/>
<meta itemprop="property" content="unbatch"/>
<meta itemprop="property" content="window"/>
<meta itemprop="property" content="with_options"/>
<meta itemprop="property" content="zip"/>
</div>

# tf.data.TFRecordDataset

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/data/ops/readers.py">View source</a>



## Class `TFRecordDataset`

A `Dataset` comprising records from one or more TFRecord files.

Inherits From: [`Dataset`](../../tf/data/Dataset.md)

<!-- Placeholder for "Used in" -->


<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/data/ops/readers.py">View source</a>

``` python
__init__(
    filenames,
    compression_type=None,
    buffer_size=None,
    num_parallel_reads=None
)
```

Creates a `TFRecordDataset` to read one or more TFRecord files.


#### Args:


* <b>`filenames`</b>: A <a href="../../tf.md#string"><code>tf.string</code></a> tensor or <a href="../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a> containing one or
  more filenames.
* <b>`compression_type`</b>: (Optional.) A <a href="../../tf.md#string"><code>tf.string</code></a> scalar evaluating to one of
  `""` (no compression), `"ZLIB"`, or `"GZIP"`.
* <b>`buffer_size`</b>: (Optional.) A <a href="../../tf.md#int64"><code>tf.int64</code></a> scalar representing the number of
  bytes in the read buffer. If your input pipeline is I/O bottlenecked,
  consider setting this parameter to a value 1-100 MBs. If `None`, a
  sensible default for both local and remote file systems is used.
* <b>`num_parallel_reads`</b>: (Optional.) A <a href="../../tf.md#int64"><code>tf.int64</code></a> scalar representing the
  number of files to read in parallel. If greater than one, the records of
  files read in parallel are outputted in an interleaved order. If your
  input pipeline is I/O bottlenecked, consider setting this parameter to a
  value greater than one to parallelize the I/O. If `None`, files will be
  read sequentially.


#### Raises:


* <b>`TypeError`</b>: If any argument does not have the expected type.
* <b>`ValueError`</b>: If any argument does not have the expected shape.



## Properties

<h3 id="element_spec"><code>element_spec</code></h3>

The type specification of an element of this dataset.

```
>>> dataset = tf.data.Dataset.from_tensor_slices([1, 2, 3]).element_spec
TensorSpec(shape=(), dtype=tf.int32, name=None)
```

#### Returns:

A nested structure of <a href="../../tf/TypeSpec.md"><code>tf.TypeSpec</code></a> objects matching the structure of an
element of this dataset and specifying the type of individual components.




## Methods

<h3 id="__iter__"><code>__iter__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/data/ops/dataset_ops.py">View source</a>

``` python
__iter__()
```

Creates an `Iterator` for enumerating the elements of this dataset.

The returned iterator implements the Python iterator protocol and therefore
can only be used in eager mode.

#### Returns:

An `Iterator` over the elements of this dataset.



#### Raises:


* <b>`RuntimeError`</b>: If not inside of tf.function and not executing eagerly.

<h3 id="apply"><code>apply</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/data/ops/dataset_ops.py">View source</a>

``` python
apply(transformation_func)
```

Applies a transformation function to this dataset.

`apply` enables chaining of custom `Dataset` transformations, which are
represented as functions that take one `Dataset` argument and return a
transformed `Dataset`.

```
>>> dataset = tf.data.Dataset.range(100)
>>> def dataset_fn(ds):
...   return ds.filter(lambda x: x < 5)
>>> dataset = dataset.apply(dataset_fn)
>>> list(dataset.as_numpy_iterator())
[0, 1, 2, 3, 4]
```

#### Args:


* <b>`transformation_func`</b>: A function that takes one `Dataset` argument and
  returns a `Dataset`.


#### Returns:


* <b>`Dataset`</b>: The `Dataset` returned by applying `transformation_func` to this
    dataset.

<h3 id="as_numpy_iterator"><code>as_numpy_iterator</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/data/ops/dataset_ops.py">View source</a>

``` python
as_numpy_iterator()
```

Returns an iterator which converts all elements of the dataset to numpy.

Use `as_numpy_iterator` to inspect the content of your dataset. To see
element shapes and types, print dataset elements directly instead of using
`as_numpy_iterator`.

```
>>> dataset = tf.data.Dataset.from_tensor_slices([1, 2, 3])
>>> for element in dataset:
...   print(element)
tf.Tensor(1, shape=(), dtype=int32)
tf.Tensor(2, shape=(), dtype=int32)
tf.Tensor(3, shape=(), dtype=int32)
```

This method requires that you are running in eager mode and the dataset's
element_spec contains only `TensorSpec` components.

```
>>> dataset = tf.data.Dataset.from_tensor_slices([1, 2, 3])
>>> for element in dataset.as_numpy_iterator():
...   print(element)
1
2
3
```

```
>>> dataset = tf.data.Dataset.from_tensor_slices([1, 2, 3])
>>> print(list(dataset.as_numpy_iterator()))
[1, 2, 3]
```

`as_numpy_iterator()` will preserve the nested structure of dataset
elements.

```
>>> dataset = tf.data.Dataset.from_tensor_slices({'a': ([1, 2], [3, 4]),
...                                               'b': [5, 6]})
>>> list(dataset.as_numpy_iterator()) == [{'a': (1, 3), 'b': 5},
...                                       {'a': (2, 4), 'b': 6}]
True
```

#### Returns:

An iterable over the elements of the dataset, with their tensors converted
to numpy arrays.



#### Raises:


* <b>`TypeError`</b>: if an element contains a non-`Tensor` value.
* <b>`RuntimeError`</b>: if eager execution is not enabled.

<h3 id="batch"><code>batch</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/data/ops/dataset_ops.py">View source</a>

``` python
batch(
    batch_size,
    drop_remainder=False
)
```

Combines consecutive elements of this dataset into batches.

```
>>> dataset = tf.data.Dataset.range(8)
>>> dataset = dataset.batch(3)
>>> list(dataset.as_numpy_iterator())
[array([0, 1, 2]), array([3, 4, 5]), array([6, 7])]
```

```
>>> dataset = tf.data.Dataset.range(8)
>>> dataset = dataset.batch(3, drop_remainder=True)
>>> list(dataset.as_numpy_iterator())
[array([0, 1, 2]), array([3, 4, 5])]
```

The components of the resulting element will have an additional outer
dimension, which will be `batch_size` (or `N % batch_size` for the last
element if `batch_size` does not divide the number of input elements `N`
evenly and `drop_remainder` is `False`). If your program depends on the
batches having the same outer dimension, you should set the `drop_remainder`
argument to `True` to prevent the smaller batch from being produced.

#### Args:


* <b>`batch_size`</b>: A <a href="../../tf.md#int64"><code>tf.int64</code></a> scalar <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing the number of
  consecutive elements of this dataset to combine in a single batch.
* <b>`drop_remainder`</b>: (Optional.) A <a href="../../tf.md#bool"><code>tf.bool</code></a> scalar <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing
  whether the last batch should be dropped in the case it has fewer than
  `batch_size` elements; the default behavior is not to drop the smaller
  batch.


#### Returns:


* <b>`Dataset`</b>: A `Dataset`.

<h3 id="cache"><code>cache</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/data/ops/dataset_ops.py">View source</a>

``` python
cache(filename='')
```

Caches the elements in this dataset.

The first time the dataset is iterated over, its elements will be cached
either in the specified file or in memory. Subsequent iterations will
use the cached data.

Note: For the cache to be finalized, the input dataset must be iterated
through in its entirety. Otherwise, subsequent iterations will not use
cached data.

```
>>> dataset = tf.data.Dataset.range(5)
>>> dataset = dataset.map(lambda x: x**2)
>>> dataset = dataset.cache()
>>> # The first time reading through the data will generate the data using
>>> # `range` and `map`.
>>> list(dataset.as_numpy_iterator())
[0, 1, 4, 9, 16]
>>> # Subsequent iterations read from the cache.
>>> list(dataset.as_numpy_iterator())
[0, 1, 4, 9, 16]
```

When caching to a file, the cached data will persist across runs. Even the
first iteration through the data will read from the cache file. Changing
the input pipeline before the call to `.cache()` will have no effect until
the cache file is removed or the filename is changed.

```
>>> dataset = tf.data.Dataset.range(5)
>>> dataset = dataset.cache("/path/to/file)  # doctest: +SKIP
>>> list(dataset.as_numpy_iterator())  # doctest: +SKIP
[0, 1, 2, 3, 4]
>>> dataset = tf.data.Dataset.range(10)
>>> dataset = dataset.cache("/path/to/file")  # Same file! # doctest: +SKIP
>>> list(dataset.as_numpy_iterator())  # doctest: +SKIP
[0, 1, 2, 3, 4]
```

Note: `cache` will produce exactly the same elements during each iteration
through the dataset. If you wish to randomize the iteration order, make sure
to call `shuffle` *after* calling `cache`.

#### Args:


* <b>`filename`</b>: A <a href="../../tf.md#string"><code>tf.string</code></a> scalar <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing the name of a
  directory on the filesystem to use for caching elements in this Dataset.
  If a filename is not provided, the dataset will be cached in memory.


#### Returns:


* <b>`Dataset`</b>: A `Dataset`.

<h3 id="concatenate"><code>concatenate</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/data/ops/dataset_ops.py">View source</a>

``` python
concatenate(dataset)
```

Creates a `Dataset` by concatenating the given dataset with this dataset.

```
>>> a = tf.data.Dataset.range(1, 4)  # ==> [ 1, 2, 3 ]
>>> b = tf.data.Dataset.range(4, 8)  # ==> [ 4, 5, 6, 7 ]
>>> ds = a.concatenate(b)
>>> list(ds.as_numpy_iterator())
[1, 2, 3, 4, 5, 6, 7]
>>> # The input dataset and dataset to be concatenated should have the same
>>> # nested structures and output types.
>>> c = tf.data.Dataset.zip((a, b))
>>> a.concatenate(c)
Traceback (most recent call last):
TypeError: Two datasets to concatenate have different types
<dtype: 'int64'> and (tf.int64, tf.int64)
>>> d = tf.data.Dataset.from_tensor_slices(["a", "b", "c"])
>>> a.concatenate(d)
Traceback (most recent call last):
TypeError: Two datasets to concatenate have different types
<dtype: 'int64'> and <dtype: 'string'>
```

#### Args:


* <b>`dataset`</b>: `Dataset` to be concatenated.


#### Returns:


* <b>`Dataset`</b>: A `Dataset`.

<h3 id="enumerate"><code>enumerate</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/data/ops/dataset_ops.py">View source</a>

``` python
enumerate(start=0)
```

Enumerates the elements of this dataset.

It is similar to python's `enumerate`.

```
>>> dataset = tf.data.Dataset.from_tensor_slices([1, 2, 3])
>>> dataset = dataset.enumerate(start=5)
>>> for element in dataset.as_numpy_iterator():
...   print(element)
(5, 1)
(6, 2)
(7, 3)
```

```
>>> # The nested structure of the input dataset determines the structure of
>>> # elements in the resulting dataset.
>>> dataset = tf.data.Dataset.from_tensor_slices([(7, 8), (9, 10)])
>>> dataset = dataset.enumerate()
>>> for element in dataset.as_numpy_iterator():
...   print(element)
(0, array([7, 8], dtype=int32))
(1, array([ 9, 10], dtype=int32))
```

#### Args:


* <b>`start`</b>: A <a href="../../tf.md#int64"><code>tf.int64</code></a> scalar <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing the start value for
  enumeration.


#### Returns:


* <b>`Dataset`</b>: A `Dataset`.

<h3 id="filter"><code>filter</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/data/ops/dataset_ops.py">View source</a>

``` python
filter(predicate)
```

Filters this dataset according to `predicate`.

```
>>> dataset = tf.data.Dataset.from_tensor_slices([1, 2, 3])
>>> dataset = dataset.filter(lambda x: x < 3)
>>> list(dataset.as_numpy_iterator())
[1, 2]
>>> # `tf.math.equal(x, y)` is required for equality comparison
>>> def filter_fn(x):
...   return tf.math.equal(x, 1)
>>> dataset = dataset.filter(filter_fn)
>>> list(dataset.as_numpy_iterator())
[1]
```

#### Args:


* <b>`predicate`</b>: A function mapping a dataset element to a boolean.


#### Returns:


* <b>`Dataset`</b>: The `Dataset` containing the elements of this dataset for which
    `predicate` is `True`.

<h3 id="flat_map"><code>flat_map</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/data/ops/dataset_ops.py">View source</a>

``` python
flat_map(map_func)
```

Maps `map_func` across this dataset and flattens the result.

Use `flat_map` if you want to make sure that the order of your dataset
stays the same. For example, to flatten a dataset of batches into a
dataset of their elements:

```
>>> dataset = Dataset.from_tensor_slices([[1, 2, 3], [4, 5, 6], [7, 8, 9]])
>>> dataset = dataset.flat_map(lambda x: Dataset.from_tensor_slices(x))
>>> list(dataset.as_numpy_iterator())
[1, 2, 3, 4, 5, 6, 7, 8, 9]
```

<a href="../../tf/data/Dataset.md#interleave"><code>tf.data.Dataset.interleave()</code></a> is a generalization of `flat_map`, since
`flat_map` produces the same output as
<a href="../../tf/data/Dataset.md#interleave"><code>tf.data.Dataset.interleave(cycle_length=1)</code></a>

#### Args:


* <b>`map_func`</b>: A function mapping a dataset element to a dataset.


#### Returns:


* <b>`Dataset`</b>: A `Dataset`.

<h3 id="from_generator"><code>from_generator</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/data/ops/dataset_ops.py">View source</a>

``` python
from_generator(
    generator,
    output_types,
    output_shapes=None,
    args=None
)
```

Creates a `Dataset` whose elements are generated by `generator`.

The `generator` argument must be a callable object that returns
an object that supports the `iter()` protocol (e.g. a generator function).
The elements generated by `generator` must be compatible with the given
`output_types` and (optional) `output_shapes` arguments.

```
>>> import itertools
>>>
>>> def gen():
...   for i in itertools.count(1):
...     yield (i, [1] * i)
>>>
>>> dataset = tf.data.Dataset.from_generator(
...      gen,
...      (tf.int64, tf.int64),
...      (tf.TensorShape([]), tf.TensorShape([None])))
>>>
>>> list(dataset.take(3).as_numpy_iterator())
[(1, array([1])), (2, array([1, 1])), (3, array([1, 1, 1]))]
```

NOTE: The current implementation of <a href="../../tf/data/Dataset.md#from_generator"><code>Dataset.from_generator()</code></a> uses
<a href="../../tf/numpy_function.md"><code>tf.numpy_function</code></a> and inherits the same constraints. In particular, it
requires the `Dataset`- and `Iterator`-related operations to be placed
on a device in the same process as the Python program that called
<a href="../../tf/data/Dataset.md#from_generator"><code>Dataset.from_generator()</code></a>. The body of `generator` will not be
serialized in a `GraphDef`, and you should not use this method if you
need to serialize your model and restore it in a different environment.

NOTE: If `generator` depends on mutable global variables or other external
state, be aware that the runtime may invoke `generator` multiple times
(in order to support repeating the `Dataset`) and at any time
between the call to <a href="../../tf/data/Dataset.md#from_generator"><code>Dataset.from_generator()</code></a> and the production of the
first element from the generator. Mutating global variables or external
state can cause undefined behavior, and we recommend that you explicitly
cache any external state in `generator` before calling
<a href="../../tf/data/Dataset.md#from_generator"><code>Dataset.from_generator()</code></a>.

#### Args:


* <b>`generator`</b>: A callable object that returns an object that supports the
  `iter()` protocol. If `args` is not specified, `generator` must take no
  arguments; otherwise it must take as many arguments as there are values
  in `args`.
* <b>`output_types`</b>: A nested structure of <a href="../../tf/dtypes/DType.md"><code>tf.DType</code></a> objects corresponding to
  each component of an element yielded by `generator`.
* <b>`output_shapes`</b>: (Optional.) A nested structure of <a href="../../tf/TensorShape.md"><code>tf.TensorShape</code></a> objects
  corresponding to each component of an element yielded by `generator`.
* <b>`args`</b>: (Optional.) A tuple of <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a> objects that will be evaluated
  and passed to `generator` as NumPy-array arguments.


#### Returns:


* <b>`Dataset`</b>: A `Dataset`.

<h3 id="from_tensor_slices"><code>from_tensor_slices</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/data/ops/dataset_ops.py">View source</a>

``` python
from_tensor_slices(tensors)
```

Creates a `Dataset` whose elements are slices of the given tensors.

The given tensors are sliced along their first dimension. This operation
preserves the structure of the input tensors, removing the first dimension
of each tensor and using it as the dataset dimension. All input tensors
must have the same size in their first dimensions.

```
>>> # Slicing a 1D tensor produces scalar tensor elements.
>>> dataset = tf.data.Dataset.from_tensor_slices([1, 2, 3])
>>> list(dataset.as_numpy_iterator())
[1, 2, 3]
```

```
>>> # Slicing a 2D tensor produces 1D tensor elements.
>>> dataset = tf.data.Dataset.from_tensor_slices([[1, 2], [3, 4]])
>>> list(dataset.as_numpy_iterator())
[array([1, 2], dtype=int32), array([3, 4], dtype=int32)]
```

```
>>> # Slicing a tuple of 1D tensors produces tuple elements containing
>>> # scalar tensors.
>>> dataset = tf.data.Dataset.from_tensor_slices(([1, 2], [3, 4], [5, 6]))
>>> list(dataset.as_numpy_iterator())
[(1, 3, 5), (2, 4, 6)]
```

```
>>> # Dictionary structure is also preserved.
>>> dataset = tf.data.Dataset.from_tensor_slices({"a": [1, 2], "b": [3, 4]})
>>> list(dataset.as_numpy_iterator()) == [{'a': 1, 'b': 3},
...                                       {'a': 2, 'b': 4}]
True
```

```
>>> # Two tensors can be combined into one Dataset object.
>>> features = tf.constant([[1, 3], [2, 1], [3, 3]]) # ==> 3x2 tensor
>>> labels = tf.constant(['A', 'B', 'A']) # ==> 3x1 tensor
>>> dataset = Dataset.from_tensor_slices((features, labels))
>>> # Both the features and the labels tensors can be converted
>>> # to a Dataset object separately and combined after.
>>> features_dataset = Dataset.from_tensor_slices(features)
>>> labels_dataset = Dataset.from_tensor_slices(labels)
>>> dataset = Dataset.zip((features_dataset, labels_dataset))
>>> # A batched feature and label set can be converted to a Dataset
>>> # in similar fashion.
>>> batched_features = tf.constant([[[1, 3], [2, 3]],
...                                 [[2, 1], [1, 2]],
...                                 [[3, 3], [3, 2]]], shape=(3, 2, 2))
>>> batched_labels = tf.constant([['A', 'A'],
...                               ['B', 'B'],
...                               ['A', 'B']], shape=(3, 2, 1))
>>> dataset = Dataset.from_tensor_slices((batched_features, batched_labels))
>>> for element in dataset.as_numpy_iterator():
...   print(element)
(array([[1, 3],
       [2, 3]], dtype=int32), array([[b'A'],
       [b'A']], dtype=object))
(array([[2, 1],
       [1, 2]], dtype=int32), array([[b'B'],
       [b'B']], dtype=object))
(array([[3, 3],
       [3, 2]], dtype=int32), array([[b'A'],
       [b'B']], dtype=object))
```

Note that if `tensors` contains a NumPy array, and eager execution is not
enabled, the values will be embedded in the graph as one or more
<a href="../../tf/constant.md"><code>tf.constant</code></a> operations. For large datasets (> 1 GB), this can waste
memory and run into byte limits of graph serialization. If `tensors`
contains one or more large NumPy arrays, consider the alternative described
in [this guide](
https://tensorflow.org/guide/data#consuming_numpy_arrays).

#### Args:


* <b>`tensors`</b>: A dataset element, with each component having the same size in
  the first dimension.


#### Returns:


* <b>`Dataset`</b>: A `Dataset`.

<h3 id="from_tensors"><code>from_tensors</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/data/ops/dataset_ops.py">View source</a>

``` python
from_tensors(tensors)
```

Creates a `Dataset` with a single element, comprising the given tensors.

```
>>> dataset = tf.data.Dataset.from_tensors([1, 2, 3])
>>> list(dataset.as_numpy_iterator())
[array([1, 2, 3], dtype=int32)]
>>> dataset = tf.data.Dataset.from_tensors(([1, 2, 3], 'A'))
>>> list(dataset.as_numpy_iterator())
[(array([1, 2, 3], dtype=int32), b'A')]
```

Note that if `tensors` contains a NumPy array, and eager execution is not
enabled, the values will be embedded in the graph as one or more
<a href="../../tf/constant.md"><code>tf.constant</code></a> operations. For large datasets (> 1 GB), this can waste
memory and run into byte limits of graph serialization. If `tensors`
contains one or more large NumPy arrays, consider the alternative described
in [this
guide](https://tensorflow.org/guide/data#consuming_numpy_arrays).

#### Args:


* <b>`tensors`</b>: A dataset element.


#### Returns:


* <b>`Dataset`</b>: A `Dataset`.

<h3 id="interleave"><code>interleave</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/data/ops/dataset_ops.py">View source</a>

``` python
interleave(
    map_func,
    cycle_length=AUTOTUNE,
    block_length=1,
    num_parallel_calls=None
)
```

Maps `map_func` across this dataset, and interleaves the results.

For example, you can use <a href="../../tf/data/Dataset.md#interleave"><code>Dataset.interleave()</code></a> to process many input files
concurrently:

```
>>> # Preprocess 4 files concurrently, and interleave blocks of 16 records
>>> # from each file.
>>> filenames = ["/var/data/file1.txt", "/var/data/file2.txt",
...              "/var/data/file3.txt", "/var/data/file4.txt"]
>>> dataset = tf.data.Dataset.from_tensor_slices(filenames)
>>> def parse_fn(filename):
...   return tf.data.Dataset.range(10)
>>> dataset = dataset.interleave(lambda x:
...     tf.data.TextLineDataset(x).map(parse_fn, num_parallel_calls=1),
...     cycle_length=4, block_length=16)
```

The `cycle_length` and `block_length` arguments control the order in which
elements are produced. `cycle_length` controls the number of input elements
that are processed concurrently. If you set `cycle_length` to 1, this
transformation will handle one input element at a time, and will produce
identical results to <a href="../../tf/data/Dataset.md#flat_map"><code>tf.data.Dataset.flat_map</code></a>. In general,
this transformation will apply `map_func` to `cycle_length` input elements,
open iterators on the returned `Dataset` objects, and cycle through them
producing `block_length` consecutive elements from each iterator, and
consuming the next input element each time it reaches the end of an
iterator.

#### For example:



```
>>> dataset = Dataset.range(1, 6)  # ==> [ 1, 2, 3, 4, 5 ]
>>> # NOTE: New lines indicate "block" boundaries.
>>> dataset = dataset.interleave(
...     lambda x: Dataset.from_tensors(x).repeat(6),
...     cycle_length=2, block_length=4)
>>> list(dataset.as_numpy_iterator())
[1, 1, 1, 1, 2, 2, 2, 2, 1, 1, 2, 2, 3, 3, 3, 3, 4, 4, 4, 4, 3, 3, 4, 4, 5, 5, 5, 5, 5, 5]
```

NOTE: The order of elements yielded by this transformation is
deterministic, as long as `map_func` is a pure function. If
`map_func` contains any stateful operations, the order in which
that state is accessed is undefined.

#### Args:


* <b>`map_func`</b>: A function mapping a dataset element to a dataset.
* <b>`cycle_length`</b>: (Optional.) The number of input elements that will be
  processed concurrently. If not specified, the value will be derived from
  the number of available CPU cores. If the `num_parallel_calls` argument
  is set to <a href="../../tf/data/experimental.md#AUTOTUNE"><code>tf.data.experimental.AUTOTUNE</code></a>, the `cycle_length` argument
  also identifies the maximum degree of parallelism.
* <b>`block_length`</b>: (Optional.) The number of consecutive elements to produce
  from each input element before cycling to another input element.
* <b>`num_parallel_calls`</b>: (Optional.) If specified, the implementation creates a
  threadpool, which is used to fetch inputs from cycle elements
  asynchronously and in parallel. The default behavior is to fetch inputs
  from cycle elements synchronously with no parallelism. If the value
  <a href="../../tf/data/experimental.md#AUTOTUNE"><code>tf.data.experimental.AUTOTUNE</code></a> is used, then the number of parallel
  calls is set dynamically based on available CPU.


#### Returns:


* <b>`Dataset`</b>: A `Dataset`.

<h3 id="list_files"><code>list_files</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/data/ops/dataset_ops.py">View source</a>

``` python
list_files(
    file_pattern,
    shuffle=None,
    seed=None
)
```

A dataset of all files matching one or more glob patterns.

The `file_pattern` argument should be a small number of glob patterns.
If your filenames have already been globbed, use
<a href="../../tf/data/Dataset.md#from_tensor_slices"><code>Dataset.from_tensor_slices(filenames)</code></a> instead, as re-globbing every
filename with `list_files` may result in poor performance with remote
storage systems.

NOTE: The default behavior of this method is to return filenames in
a non-deterministic random shuffled order. Pass a `seed` or `shuffle=False`
to get results in a deterministic order.

#### Example:

If we had the following files on our filesystem:
  - /path/to/dir/a.txt
  - /path/to/dir/b.py
  - /path/to/dir/c.py
If we pass "/path/to/dir/*.py" as the directory, the dataset
would produce:
  - /path/to/dir/b.py
  - /path/to/dir/c.py



#### Args:


* <b>`file_pattern`</b>: A string, a list of strings, or a <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a> of string type
  (scalar or vector), representing the filename glob (i.e. shell wildcard)
  pattern(s) that will be matched.
* <b>`shuffle`</b>: (Optional.) If `True`, the file names will be shuffled randomly.
  Defaults to `True`.
* <b>`seed`</b>: (Optional.) A <a href="../../tf.md#int64"><code>tf.int64</code></a> scalar <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing the random
  seed that will be used to create the distribution. See
  <a href="../../tf/compat/v1/set_random_seed.md"><code>tf.compat.v1.set_random_seed</code></a> for behavior.


#### Returns:


* <b>`Dataset`</b>: A `Dataset` of strings corresponding to file names.

<h3 id="map"><code>map</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/data/ops/dataset_ops.py">View source</a>

``` python
map(
    map_func,
    num_parallel_calls=None
)
```

Maps `map_func` across the elements of this dataset.

This transformation applies `map_func` to each element of this dataset, and
returns a new dataset containing the transformed elements, in the same
order as they appeared in the input. `map_func` can be used to change both
the values and the structure of a dataset's elements. For example, adding 1
to each element, or projecting a subset of element components.

```
>>> dataset = Dataset.range(1, 6)  # ==> [ 1, 2, 3, 4, 5 ]
>>> dataset = dataset.map(lambda x: x + 1)
>>> list(dataset.as_numpy_iterator())
[2, 3, 4, 5, 6]
```

The input signature of `map_func` is determined by the structure of each
element in this dataset.

```
>>> dataset = Dataset.range(5)
>>> # `map_func` takes a single argument of type `tf.Tensor` with the same
>>> # shape and dtype.
>>> result = dataset.map(lambda x: x + 1)
```

```
>>> # Each element is a tuple containing two `tf.Tensor` objects.
>>> elements = [(1, "foo"), (2, "bar"), (3, "baz)")]
>>> dataset = tf.data.Dataset.from_generator(
...     lambda: elements, (tf.int32, tf.string))
>>> # `map_func` takes two arguments of type `tf.Tensor`. This function
>>> # projects out just the first component.
>>> result = dataset.map(lambda x_int, y_str: x_int)
>>> list(result.as_numpy_iterator())
[1, 2, 3]
```

```
>>> # Each element is a dictionary mapping strings to `tf.Tensor` objects.
>>> elements =  ([{"a": 1, "b": "foo"},
...               {"a": 2, "b": "bar"},
...               {"a": 3, "b": "baz"}])
>>> dataset = tf.data.Dataset.from_generator(
...     lambda: elements, {"a": tf.int32, "b": tf.string})
>>> # `map_func` takes a single argument of type `dict` with the same keys
>>> # as the elements.
>>> result = dataset.map(lambda d: str(d["a"]) + d["b"])
```

The value or values returned by `map_func` determine the structure of each
element in the returned dataset.

```
>>> dataset = tf.data.Dataset.range(3)
>>> # `map_func` returns two `tf.Tensor` objects.
>>> def g(x):
...   return tf.constant(37.0), tf.constant(["Foo", "Bar", "Baz"])
>>> result = dataset.map(g)
>>> result.element_spec
(TensorSpec(shape=(), dtype=tf.float32, name=None), TensorSpec(shape=(3,), dtype=tf.string, name=None))
>>> # Python primitives, lists, and NumPy arrays are implicitly converted to
>>> # `tf.Tensor`.
>>> def h(x):
...   return 37.0, ["Foo", "Bar"], np.array([1.0, 2.0], dtype=np.float64)
>>> result = dataset.map(h)
>>> result.element_spec
(TensorSpec(shape=(), dtype=tf.float32, name=None), TensorSpec(shape=(2,), dtype=tf.string, name=None), TensorSpec(shape=(2,), dtype=tf.float64, name=None))
>>> # `map_func` can return nested structures.
>>> def i(x):
...   return (37.0, [42, 16]), "foo"
>>> result = dataset.map(i)
>>> result.element_spec
((TensorSpec(shape=(), dtype=tf.float32, name=None),
  TensorSpec(shape=(2,), dtype=tf.int32, name=None)),
 TensorSpec(shape=(), dtype=tf.string, name=None))
```

`map_func` can accept as arguments and return any type of dataset element.

Note that irrespective of the context in which `map_func` is defined (eager
vs. graph), tf.data traces the function and executes it as a graph. To use
Python code inside of the function you have two options:

1) Rely on AutoGraph to convert Python code into an equivalent graph
computation. The downside of this approach is that AutoGraph can convert
some but not all Python code.

2) Use <a href="../../tf/py_function.md"><code>tf.py_function</code></a>, which allows you to write arbitrary Python code but
will generally result in worse performance than 1). For example:

```
>>> d = tf.data.Dataset.from_tensor_slices(['hello', 'world'])
>>> # transform a string tensor to upper case string using a Python function
>>> def upper_case_fn(t: tf.Tensor):
...   return t.numpy().decode('utf-8').upper()
>>> d = d.map(lambda x: tf.py_function(func=upper_case_fn,
...           inp=[x], Tout=tf.string))
>>> list(d.as_numpy_iterator())
[b'HELLO', b'WORLD']
```

#### Args:


* <b>`map_func`</b>: A function mapping a dataset element to another dataset element.
* <b>`num_parallel_calls`</b>: (Optional.) A <a href="../../tf.md#int32"><code>tf.int32</code></a> scalar <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a>,
  representing the number elements to process asynchronously in parallel.
  If not specified, elements will be processed sequentially. If the value
  <a href="../../tf/data/experimental.md#AUTOTUNE"><code>tf.data.experimental.AUTOTUNE</code></a> is used, then the number of parallel
  calls is set dynamically based on available CPU.


#### Returns:


* <b>`Dataset`</b>: A `Dataset`.

<h3 id="options"><code>options</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/data/ops/dataset_ops.py">View source</a>

``` python
options()
```

Returns the options for this dataset and its inputs.


#### Returns:

A <a href="../../tf/data/Options.md"><code>tf.data.Options</code></a> object representing the dataset options.


<h3 id="padded_batch"><code>padded_batch</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/data/ops/dataset_ops.py">View source</a>

``` python
padded_batch(
    batch_size,
    padded_shapes,
    padding_values=None,
    drop_remainder=False
)
```

Combines consecutive elements of this dataset into padded batches.

This transformation combines multiple consecutive elements of the input
dataset into a single element.

Like <a href="../../tf/data/Dataset.md#batch"><code>tf.data.Dataset.batch</code></a>, the components of the resulting element will
have an additional outer dimension, which will be `batch_size` (or
`N % batch_size` for the last element if `batch_size` does not divide the
number of input elements `N` evenly and `drop_remainder` is `False`). If
your program depends on the batches having the same outer dimension, you
should set the `drop_remainder` argument to `True` to prevent the smaller
batch from being produced.

Unlike <a href="../../tf/data/Dataset.md#batch"><code>tf.data.Dataset.batch</code></a>, the input elements to be batched may have
different shapes, and this transformation will pad each component to the
respective shape in `padding_shapes`. The `padding_shapes` argument
determines the resulting shape for each dimension of each component in an
output element:

* If the dimension is a constant (e.g. <a href="../../tf/compat/v1/Dimension.md"><code>tf.compat.v1.Dimension(37)</code></a>), the
component will be padded out to that length in that dimension.
* If the dimension is unknown (e.g. <a href="../../tf/compat/v1/Dimension.md"><code>tf.compat.v1.Dimension(None)</code></a>), the
component will be padded out to the maximum length of all elements in that
dimension.

```
>>> elements = [[1, 2],
...             [3, 4, 5],
...             [6, 7],
...             [8]]
>>> A = tf.data.Dataset.from_generator(lambda: iter(elements), tf.int32)
>>> # Pad to the smallest per-batch size that fits all elements.
>>> B = A.padded_batch(2, padded_shapes=[None])
>>> for element in B.as_numpy_iterator():
...   print(element)
[[1 2 0]
 [3 4 5]]
[[6 7]
 [8 0]]
>>> # Pad to a fixed size.
>>> C = A.padded_batch(2, padded_shapes=3)
>>> for element in C.as_numpy_iterator():
...   print(element)
[[1 2 0]
 [3 4 5]]
[[6 7 0]
 [8 0 0]]
>>> # Pad with a custom value.
>>> D = A.padded_batch(2, padded_shapes=3, padding_values=-1)
>>> for element in D.as_numpy_iterator():
...   print(element)
[[ 1  2 -1]
 [ 3  4  5]]
[[ 6  7 -1]
 [ 8 -1 -1]]
>>> # Components of nested elements can be padded independently.
>>> elements = [([1, 2, 3], [10]),
...             ([4, 5], [11, 12])]
>>> dataset = tf.data.Dataset.from_generator(
...     lambda: iter(elements), (tf.int32, tf.int32))
>>> # Pad the first component of the tuple to length 4, and the second
>>> # component to the smallest size that fits.
>>> dataset = dataset.padded_batch(2,
...     padded_shapes=([4], [None]),
...     padding_values=(-1, 100))
>>> list(dataset.as_numpy_iterator())
[(array([[ 1,  2,  3, -1], [ 4,  5, -1, -1]], dtype=int32),
  array([[ 10, 100], [ 11,  12]], dtype=int32))]
```

See also <a href="../../tf/data/experimental/dense_to_sparse_batch.md"><code>tf.data.experimental.dense_to_sparse_batch</code></a>, which combines
elements that may have different shapes into a <a href="../../tf/sparse/SparseTensor.md"><code>tf.SparseTensor</code></a>.

#### Args:


* <b>`batch_size`</b>: A <a href="../../tf.md#int64"><code>tf.int64</code></a> scalar <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing the number of
  consecutive elements of this dataset to combine in a single batch.
* <b>`padded_shapes`</b>: A nested structure of <a href="../../tf/TensorShape.md"><code>tf.TensorShape</code></a> or <a href="../../tf.md#int64"><code>tf.int64</code></a> vector
  tensor-like objects representing the shape to which the respective
  component of each input element should be padded prior to batching. Any
  unknown dimensions (e.g. <a href="../../tf/compat/v1/Dimension.md"><code>tf.compat.v1.Dimension(None)</code></a> in a
  <a href="../../tf/TensorShape.md"><code>tf.TensorShape</code></a> or `-1` in a tensor-like object) will be padded to the
  maximum size of that dimension in each batch.
* <b>`padding_values`</b>: (Optional.) A nested structure of scalar-shaped
  <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing the padding values to use for the respective
  components. None represents that the nested structure should be padded
  with default values.  Defaults are `0` for numeric types and the empty
  string for string types.
* <b>`drop_remainder`</b>: (Optional.) A <a href="../../tf.md#bool"><code>tf.bool</code></a> scalar <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing
  whether the last batch should be dropped in the case it has fewer than
  `batch_size` elements; the default behavior is not to drop the smaller
  batch.


#### Returns:


* <b>`Dataset`</b>: A `Dataset`.

<h3 id="prefetch"><code>prefetch</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/data/ops/dataset_ops.py">View source</a>

``` python
prefetch(buffer_size)
```

Creates a `Dataset` that prefetches elements from this dataset.

Most dataset input pipelines should end with a call to `prefetch`. This
allows later elements to be prepared while the current element is being
processed. This often improves latency and throughput, at the cost of
using additional memory to store prefetched elements.

Note: Like other `Dataset` methods, prefetch operates on the
elements of the input dataset. It has no concept of examples vs. batches.
`examples.prefetch(2)` will prefetch two elements (2 examples),
while `examples.batch(20).prefetch(2)` will prefetch 2 elements
(2 batches, of 20 examples each).

```
>>> dataset = tf.data.Dataset.range(3)
>>> dataset = dataset.prefetch(2)
>>> list(dataset.as_numpy_iterator())
[0, 1, 2]
```

#### Args:


* <b>`buffer_size`</b>: A <a href="../../tf.md#int64"><code>tf.int64</code></a> scalar <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing the maximum
  number of elements that will be buffered when prefetching.


#### Returns:


* <b>`Dataset`</b>: A `Dataset`.

<h3 id="range"><code>range</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/data/ops/dataset_ops.py">View source</a>

``` python
range(
    *args,
    **kwargs
)
```

Creates a `Dataset` of a step-separated range of values.

```
>>> list(Dataset.range(5).as_numpy_iterator())
[0, 1, 2, 3, 4]
>>> list(Dataset.range(2, 5).as_numpy_iterator())
[2, 3, 4]
>>> list(Dataset.range(1, 5, 2).as_numpy_iterator())
[1, 3]
>>> list(Dataset.range(1, 5, -2).as_numpy_iterator())
[]
>>> list(Dataset.range(5, 1).as_numpy_iterator())
[]
>>> list(Dataset.range(5, 1, -2).as_numpy_iterator())
[5, 3]
>>> list(Dataset.range(2, 5, output_type=tf.int32).as_numpy_iterator())
[2, 3, 4]
>>> list(Dataset.range(1, 5, 2, output_type=tf.float32).as_numpy_iterator())
[1.0, 3.0]
```

#### Args:


* <b>`*args`</b>: follows the same semantics as python's xrange.
  len(args) == 1 -> start = 0, stop = args[0], step = 1
  len(args) == 2 -> start = args[0], stop = args[1], step = 1
  len(args) == 3 -> start = args[0], stop = args[1, stop = args[2]
* <b>`**kwargs`</b>:   - output_type: Its expected dtype. (Optional, default: <a href="../../tf.md#int64"><code>tf.int64</code></a>).


#### Returns:


* <b>`Dataset`</b>: A `RangeDataset`.


#### Raises:


* <b>`ValueError`</b>: if len(args) == 0.

<h3 id="reduce"><code>reduce</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/data/ops/dataset_ops.py">View source</a>

``` python
reduce(
    initial_state,
    reduce_func
)
```

Reduces the input dataset to a single element.

The transformation calls `reduce_func` successively on every element of
the input dataset until the dataset is exhausted, aggregating information in
its internal state. The `initial_state` argument is used for the initial
state and the final state is returned as the result.

```
>>> tf.data.Dataset.range(5).reduce(np.int64(0), lambda x, _: x + 1).numpy()
5
>>> tf.data.Dataset.range(5).reduce(np.int64(0), lambda x, y: x + y).numpy()
10
```

#### Args:


* <b>`initial_state`</b>: An element representing the initial state of the
  transformation.
* <b>`reduce_func`</b>: A function that maps `(old_state, input_element)` to
  `new_state`. It must take two arguments and return a new element
  The structure of `new_state` must match the structure of
  `initial_state`.


#### Returns:

A dataset element corresponding to the final state of the transformation.


<h3 id="repeat"><code>repeat</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/data/ops/dataset_ops.py">View source</a>

``` python
repeat(count=None)
```

Repeats this dataset so each original value is seen `count` times.

```
>>> dataset = tf.data.Dataset.from_tensor_slices([1, 2, 3])
>>> dataset = dataset.repeat(3)
>>> list(dataset.as_numpy_iterator())
[1, 2, 3, 1, 2, 3, 1, 2, 3]
```

NOTE: If this dataset is a function of global state (e.g. a random number
generator), then different repetitions may produce different elements.

#### Args:


* <b>`count`</b>: (Optional.) A <a href="../../tf.md#int64"><code>tf.int64</code></a> scalar <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing the
  number of times the dataset should be repeated. The default behavior (if
  `count` is `None` or `-1`) is for the dataset be repeated indefinitely.


#### Returns:


* <b>`Dataset`</b>: A `Dataset`.

<h3 id="shard"><code>shard</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/data/ops/dataset_ops.py">View source</a>

``` python
shard(
    num_shards,
    index
)
```

Creates a `Dataset` that includes only 1/`num_shards` of this dataset.

`shard` is deterministic. The Dataset produced by `A.shard(n, i)` will
contain all elements of A whose index mod n = i.

```
>>> A = tf.data.Dataset.range(10)
>>> B = A.shard(num_shards=3, index=0)
>>> list(B.as_numpy_iterator())
[0, 3, 6, 9]
>>> C = A.shard(num_shards=3, index=1)
>>> list(C.as_numpy_iterator())
[1, 4, 7]
>>> D = A.shard(num_shards=3, index=2)
>>> list(D.as_numpy_iterator())
[2, 5, 8]
```

This dataset operator is very useful when running distributed training, as
it allows each worker to read a unique subset.

When reading a single input file, you can shard elements as follows:

```python
d = tf.data.TFRecordDataset(input_file)
d = d.shard(num_workers, worker_index)
d = d.repeat(num_epochs)
d = d.shuffle(shuffle_buffer_size)
d = d.map(parser_fn, num_parallel_calls=num_map_threads)
```

#### Important caveats:



- Be sure to shard before you use any randomizing operator (such as
  shuffle).
- Generally it is best if the shard operator is used early in the dataset
  pipeline. For example, when reading from a set of TFRecord files, shard
  before converting the dataset to input samples. This avoids reading every
  file on every worker. The following is an example of an efficient
  sharding strategy within a complete pipeline:

```python
d = Dataset.list_files(pattern)
d = d.shard(num_workers, worker_index)
d = d.repeat(num_epochs)
d = d.shuffle(shuffle_buffer_size)
d = d.interleave(tf.data.TFRecordDataset,
                 cycle_length=num_readers, block_length=1)
d = d.map(parser_fn, num_parallel_calls=num_map_threads)
```

#### Args:


* <b>`num_shards`</b>: A <a href="../../tf.md#int64"><code>tf.int64</code></a> scalar <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing the number of
  shards operating in parallel.
* <b>`index`</b>: A <a href="../../tf.md#int64"><code>tf.int64</code></a> scalar <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing the worker index.


#### Returns:


* <b>`Dataset`</b>: A `Dataset`.


#### Raises:


* <b>`InvalidArgumentError`</b>: if `num_shards` or `index` are illegal values.
  Note: error checking is done on a best-effort basis, and errors aren't
  guaranteed to be caught upon dataset creation. (e.g. providing in a
  placeholder tensor bypasses the early checking, and will instead result
  in an error during a session.run call.)

<h3 id="shuffle"><code>shuffle</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/data/ops/dataset_ops.py">View source</a>

``` python
shuffle(
    buffer_size,
    seed=None,
    reshuffle_each_iteration=None
)
```

Randomly shuffles the elements of this dataset.

This dataset fills a buffer with `buffer_size` elements, then randomly
samples elements from this buffer, replacing the selected elements with new
elements. For perfect shuffling, a buffer size greater than or equal to the
full size of the dataset is required.

For instance, if your dataset contains 10,000 elements but `buffer_size` is
set to 1,000, then `shuffle` will initially select a random element from
only the first 1,000 elements in the buffer. Once an element is selected,
its space in the buffer is replaced by the next (i.e. 1,001-st) element,
maintaining the 1,000 element buffer.

`reshuffle_each_iteration` controls whether the shuffle order should be
different for each epoch. In TF 1.X, the idiomatic way to create epochs
was through the `repeat` transformation:

```
>>> dataset = tf.data.Dataset.range(3)
>>> dataset = dataset.shuffle(3, reshuffle_each_iteration=True)
>>> dataset = dataset.repeat(2)  # doctest: +SKIP
[1, 0, 2, 1, 2, 0]
```

```
>>> dataset = tf.data.Dataset.range(3)
>>> dataset = dataset.shuffle(3, reshuffle_each_iteration=False)
>>> dataset = dataset.repeat(2)  # doctest: +SKIP
[1, 0, 2, 1, 0, 2]
```

In TF 2.0, <a href="../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a> objects are Python iterables which makes it
possible to also create epochs through Python iteration:

```
>>> dataset = tf.data.Dataset.range(3)
>>> dataset = dataset.shuffle(3, reshuffle_each_iteration=True)
>>> list(dataset.as_numpy_iterator())  # doctest: +SKIP
[1, 0, 2]
>>> list(dataset.as_numpy_iterator())  # doctest: +SKIP
[1, 2, 0]
```

```
>>> dataset = tf.data.Dataset.range(3)
>>> dataset = dataset.shuffle(3, reshuffle_each_iteration=False)
>>> list(dataset.as_numpy_iterator())  # doctest: +SKIP
[1, 0, 2]
>>> list(dataset.as_numpy_iterator())  # doctest: +SKIP
[1, 0, 2]
```

#### Args:


* <b>`buffer_size`</b>: A <a href="../../tf.md#int64"><code>tf.int64</code></a> scalar <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing the number of
  elements from this dataset from which the new dataset will sample.
* <b>`seed`</b>: (Optional.) A <a href="../../tf.md#int64"><code>tf.int64</code></a> scalar <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing the random
  seed that will be used to create the distribution. See
  <a href="../../tf/compat/v1/set_random_seed.md"><code>tf.compat.v1.set_random_seed</code></a> for behavior.
* <b>`reshuffle_each_iteration`</b>: (Optional.) A boolean, which if true indicates
  that the dataset should be pseudorandomly reshuffled each time it is
  iterated over. (Defaults to `True`.)


#### Returns:


* <b>`Dataset`</b>: A `Dataset`.

<h3 id="skip"><code>skip</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/data/ops/dataset_ops.py">View source</a>

``` python
skip(count)
```

Creates a `Dataset` that skips `count` elements from this dataset.

```
>>> dataset = tf.data.Dataset.range(10)
>>> dataset = dataset.skip(7)
>>> list(dataset.as_numpy_iterator())
[7, 8, 9]
```

#### Args:


* <b>`count`</b>: A <a href="../../tf.md#int64"><code>tf.int64</code></a> scalar <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing the number of
  elements of this dataset that should be skipped to form the new dataset.
  If `count` is greater than the size of this dataset, the new dataset
  will contain no elements.  If `count` is -1, skips the entire dataset.


#### Returns:


* <b>`Dataset`</b>: A `Dataset`.

<h3 id="take"><code>take</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/data/ops/dataset_ops.py">View source</a>

``` python
take(count)
```

Creates a `Dataset` with at most `count` elements from this dataset.

```
>>> dataset = tf.data.Dataset.range(10)
>>> dataset = dataset.take(3)
>>> list(dataset.as_numpy_iterator())
[0, 1, 2]
```

#### Args:


* <b>`count`</b>: A <a href="../../tf.md#int64"><code>tf.int64</code></a> scalar <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing the number of
  elements of this dataset that should be taken to form the new dataset.
  If `count` is -1, or if `count` is greater than the size of this
  dataset, the new dataset will contain all elements of this dataset.


#### Returns:


* <b>`Dataset`</b>: A `Dataset`.

<h3 id="unbatch"><code>unbatch</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/data/ops/dataset_ops.py">View source</a>

``` python
unbatch()
```

Splits elements of a dataset into multiple elements.

For example, if elements of the dataset are shaped `[B, a0, a1, ...]`,
where `B` may vary for each input element, then for each element in the
dataset, the unbatched dataset will contain `B` consecutive elements
of shape `[a0, a1, ...]`.

```
>>> elements = [ [1, 2, 3], [1, 2], [1, 2, 3, 4] ]
>>> dataset = tf.data.Dataset.from_generator(lambda: elements, tf.int64)
>>> dataset = dataset.unbatch()
>>> list(dataset.as_numpy_iterator())
[1, 2, 3, 1, 2, 1, 2, 3, 4]
```

#### Returns:

A `Dataset` transformation function, which can be passed to
<a href="../../tf/data/Dataset.md#apply"><code>tf.data.Dataset.apply</code></a>.


<h3 id="window"><code>window</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/data/ops/dataset_ops.py">View source</a>

``` python
window(
    size,
    shift=None,
    stride=1,
    drop_remainder=False
)
```

Combines (nests of) input elements into a dataset of (nests of) windows.

A "window" is a finite dataset of flat elements of size `size` (or possibly
fewer if there are not enough input elements to fill the window and
`drop_remainder` evaluates to false).

The `stride` argument determines the stride of the input elements, and the
`shift` argument determines the shift of the window.

```
>>> dataset = tf.data.Dataset.range(7).window(2)
>>> for window in dataset:
...   print(list(window.as_numpy_iterator()))
[0, 1]
[2, 3]
[4, 5]
[6]
>>> dataset = tf.data.Dataset.range(7).window(3, 2, 1, True)
>>> for window in dataset:
...   print(list(window.as_numpy_iterator()))
[0, 1, 2]
[2, 3, 4]
[4, 5, 6]
>>> dataset = tf.data.Dataset.range(7).window(3, 1, 2, True)
>>> for window in dataset:
...   print(list(window.as_numpy_iterator()))
[0, 2, 4]
[1, 3, 5]
[2, 4, 6]
```

Note that when the `window` transformation is applied to a dataset of
nested elements, it produces a dataset of nested windows.

```
>>> nested = ([1, 2, 3, 4], [5, 6, 7, 8])
>>> dataset = tf.data.Dataset.from_tensor_slices(nested).window(2)
>>> for window in dataset:
...   def to_numpy(ds):
...     return list(ds.as_numpy_iterator())
...   print(tuple(to_numpy(component) for component in window))
([1, 2], [5, 6])
([3, 4], [7, 8])
```

```
>>> dataset = tf.data.Dataset.from_tensor_slices({'a': [1, 2, 3, 4]})
>>> dataset = dataset.window(2)
>>> for window in dataset:
...   def to_numpy(ds):
...     return list(ds.as_numpy_iterator())
...   print({'a': to_numpy(window['a'])})
{'a': [1, 2]}
{'a': [3, 4]}
```

#### Args:


* <b>`size`</b>: A <a href="../../tf.md#int64"><code>tf.int64</code></a> scalar <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing the number of elements
  of the input dataset to combine into a window.
* <b>`shift`</b>: (Optional.) A <a href="../../tf.md#int64"><code>tf.int64</code></a> scalar <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing the
  forward shift of the sliding window in each iteration. Defaults to
  `size`.
* <b>`stride`</b>: (Optional.) A <a href="../../tf.md#int64"><code>tf.int64</code></a> scalar <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing the
  stride of the input elements in the sliding window.
* <b>`drop_remainder`</b>: (Optional.) A <a href="../../tf.md#bool"><code>tf.bool</code></a> scalar <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing
  whether a window should be dropped in case its size is smaller than
  `window_size`.


#### Returns:


* <b>`Dataset`</b>: A `Dataset` of (nests of) windows -- a finite datasets of flat
  elements created from the (nests of) input elements.

<h3 id="with_options"><code>with_options</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/data/ops/dataset_ops.py">View source</a>

``` python
with_options(options)
```

Returns a new <a href="../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a> with the given options set.

The options are "global" in the sense they apply to the entire dataset.
If options are set multiple times, they are merged as long as different
options do not use different non-default values.

```
>>> ds = tf.data.Dataset.range(5)
>>> ds = ds.interleave(lambda x: tf.data.Dataset.range(5),
...                    cycle_length=3,
...                    num_parallel_calls=3)
>>> options = tf.data.Options()
>>> # This will make the interleave order non-deterministic.
>>> options.experimental_deterministic = False
>>> ds = ds.with_options(options)
```

#### Args:


* <b>`options`</b>: A <a href="../../tf/data/Options.md"><code>tf.data.Options</code></a> that identifies the options the use.


#### Returns:


* <b>`Dataset`</b>: A `Dataset` with the given options.


#### Raises:


* <b>`ValueError`</b>: when an option is set more than once to a non-default value

<h3 id="zip"><code>zip</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/data/ops/dataset_ops.py">View source</a>

``` python
zip(datasets)
```

Creates a `Dataset` by zipping together the given datasets.

This method has similar semantics to the built-in `zip()` function
in Python, with the main difference being that the `datasets`
argument can be an arbitrary nested structure of `Dataset` objects.

```
>>> # The nested structure of the `datasets` argument determines the
>>> # structure of elements in the resulting dataset.
>>> a = tf.data.Dataset.range(1, 4)  # ==> [ 1, 2, 3 ]
>>> b = tf.data.Dataset.range(4, 7)  # ==> [ 4, 5, 6 ]
>>> ds = tf.data.Dataset.zip((a, b))
>>> list(ds.as_numpy_iterator())
[(1, 4), (2, 5), (3, 6)]
>>> ds = tf.data.Dataset.zip((b, a))
>>> list(ds.as_numpy_iterator())
[(4, 1), (5, 2), (6, 3)]
>>>
>>> # The `datasets` argument may contain an arbitrary number of datasets.
>>> c = tf.data.Dataset.range(7, 13).batch(2)  # ==> [ [7, 8],
...                                            #       [9, 10],
...                                            #       [11, 12] ]
>>> ds = tf.data.Dataset.zip((a, b, c))
>>> for element in ds.as_numpy_iterator():
...   print(element)
(1, 4, array([7, 8]))
(2, 5, array([ 9, 10]))
(3, 6, array([11, 12]))
>>>
>>> # The number of elements in the resulting dataset is the same as
>>> # the size of the smallest dataset in `datasets`.
>>> d = tf.data.Dataset.range(13, 15)  # ==> [ 13, 14 ]
>>> ds = tf.data.Dataset.zip((a, d))
>>> list(ds.as_numpy_iterator())
[(1, 13), (2, 14)]
```

#### Args:


* <b>`datasets`</b>: A nested structure of datasets.


#### Returns:


* <b>`Dataset`</b>: A `Dataset`.





## Compat aliases

* `tf.compat.v2.data.TFRecordDataset`

