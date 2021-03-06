<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.estimator.inputs.pandas_input_fn" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.estimator.inputs.pandas_input_fn

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">

<td>
  <a target="_blank" href="https://github.com/tensorflow/estimator/tree/master/tensorflow_estimator/python/estimator/inputs/pandas_io.py">
    <img src="https://www.tensorflow.org/images/GitHub-Mark-32px.png" />
    View source on GitHub
  </a>
</td></table>



Returns input function that would feed Pandas DataFrame into the model.

``` python
tf.compat.v1.estimator.inputs.pandas_input_fn(
    x,
    y=None,
    batch_size=128,
    num_epochs=1,
    shuffle=None,
    queue_capacity=1000,
    num_threads=1,
    target_column='target'
)
```



<!-- Placeholder for "Used in" -->

Note: `y`'s index must match `x`'s index.

#### Args:


* <b>`x`</b>: pandas `DataFrame` object.
* <b>`y`</b>: pandas `Series` object or `DataFrame`. `None` if absent.
* <b>`batch_size`</b>: int, size of batches to return.
* <b>`num_epochs`</b>: int, number of epochs to iterate over data. If not `None`,
  read attempts that would exceed this value will raise `OutOfRangeError`.
* <b>`shuffle`</b>: bool, whether to read the records in random order.
* <b>`queue_capacity`</b>: int, size of the read queue. If `None`, it will be set
  roughly to the size of `x`.
* <b>`num_threads`</b>: Integer, number of threads used for reading and enqueueing. In
  order to have predicted and repeatable order of reading and enqueueing,
  such as in prediction and evaluation mode, `num_threads` should be 1.
* <b>`target_column`</b>: str, name to give the target column `y`. This parameter
  is not used when `y` is a `DataFrame`.


#### Returns:

Function, that has signature of ()->(dict of `features`, `target`)



#### Raises:


* <b>`ValueError`</b>: if `x` already contains a column with the same name as `y`, or
  if the indexes of `x` and `y` don't match.
* <b>`ValueError`</b>: if 'shuffle' is not provided or a bool.

