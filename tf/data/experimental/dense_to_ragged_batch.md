<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.data.experimental.dense_to_ragged_batch" />
<meta itemprop="path" content="Stable" />
</div>

# tf.data.experimental.dense_to_ragged_batch

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/data/experimental/ops/batching.py">View source</a>



A transformation that batches ragged elements into <a href="../../../tf/RaggedTensor.md"><code>tf.RaggedTensor</code></a>s.

``` python
tf.data.experimental.dense_to_ragged_batch(
    batch_size,
    drop_remainder=False,
    row_splits_dtype=tf.dtypes.int64
)
```



<!-- Placeholder for "Used in" -->

This transformation combines multiple consecutive elements of the input
dataset into a single element.

Like <a href="../../../tf/data/Dataset.md#batch"><code>tf.data.Dataset.batch</code></a>, the components of the resulting element will
have an additional outer dimension, which will be `batch_size` (or
`N % batch_size` for the last element if `batch_size` does not divide the
number of input elements `N` evenly and `drop_remainder` is `False`). If
your program depends on the batches having the same outer dimension, you
should set the `drop_remainder` argument to `True` to prevent the smaller
batch from being produced.

Unlike <a href="../../../tf/data/Dataset.md#batch"><code>tf.data.Dataset.batch</code></a>, the input elements to be batched may have
different shapes, and each batch will be encoded as a <a href="../../../tf/RaggedTensor.md"><code>tf.RaggedTensor</code></a>.
Example:

```
>>> dataset = tf.data.Dataset.from_tensor_slices(np.arange(6))
>>> dataset = dataset.map(lambda x: tf.range(x))
>>> dataset = dataset.apply(
...     tf.data.experimental.dense_to_ragged_batch(batch_size=2))
>>> for batch in dataset:
...   print(batch)
<tf.RaggedTensor [[], [0]]>
<tf.RaggedTensor [[0, 1], [0, 1, 2]]>
<tf.RaggedTensor [[0, 1, 2, 3], [0, 1, 2, 3, 4]]>
```

#### Args:


* <b>`batch_size`</b>: A <a href="../../../tf.md#int64"><code>tf.int64</code></a> scalar <a href="../../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing the number of
  consecutive elements of this dataset to combine in a single batch.
* <b>`drop_remainder`</b>: (Optional.) A <a href="../../../tf.md#bool"><code>tf.bool</code></a> scalar <a href="../../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing
  whether the last batch should be dropped in the case it has fewer than
  `batch_size` elements; the default behavior is not to drop the smaller
  batch.
* <b>`row_splits_dtype`</b>: The dtype that should be used for the `row_splits` of any
  new ragged tensors.  Existing <a href="../../../tf/RaggedTensor.md"><code>tf.RaggedTensor</code></a> elements do not have their
  row_splits dtype changed.


#### Returns:


* <b>`Dataset`</b>: A `Dataset`.

## Compat aliases

* `tf.compat.v1.data.experimental.dense_to_ragged_batch`
* `tf.compat.v2.data.experimental.dense_to_ragged_batch`

