<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.sort" />
<meta itemprop="path" content="Stable" />
</div>

# tf.sort

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/sort_ops.py">View source</a>



Sorts a tensor.

``` python
tf.sort(
    values,
    axis=-1,
    direction='ASCENDING',
    name=None
)
```



<!-- Placeholder for "Used in" -->


#### Usage:



```python
import tensorflow as tf
a = [1, 10, 26.9, 2.8, 166.32, 62.3]
b = tf.sort(a,axis=-1,direction='ASCENDING',name=None)
c = tf.keras.backend.eval(b)
# Here, c = [  1.     2.8   10.    26.9   62.3  166.32]
```

#### Args:


* <b>`values`</b>: 1-D or higher numeric `Tensor`.
* <b>`axis`</b>: The axis along which to sort. The default is -1, which sorts the last
  axis.
* <b>`direction`</b>: The direction in which to sort the values (`'ASCENDING'` or
  `'DESCENDING'`).
* <b>`name`</b>: Optional name for the operation.


#### Returns:

A `Tensor` with the same dtype and shape as `values`, with the elements
    sorted along the given `axis`.



#### Raises:


* <b>`ValueError`</b>: If axis is not a constant scalar, or the direction is invalid.

## Compat aliases

* `tf.compat.v1.sort`
* `tf.compat.v2.sort`

