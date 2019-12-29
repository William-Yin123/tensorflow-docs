<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.accumulate_n" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.accumulate_n

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/math_ops.py">View source</a>



Returns the element-wise sum of a list of tensors.

``` python
tf.math.accumulate_n(
    inputs,
    shape=None,
    tensor_dtype=None,
    name=None
)
```



<!-- Placeholder for "Used in" -->

Optionally, pass `shape` and `tensor_dtype` for shape and type checking,
otherwise, these are inferred.

`accumulate_n` performs the same operation as <a href="../../tf/math/add_n.md"><code>tf.math.add_n</code></a>.

#### For example:



```python
a = tf.constant([[1, 2], [3, 4]])
b = tf.constant([[5, 0], [0, 6]])
tf.math.accumulate_n([a, b, a])  # [[7, 4], [6, 14]]

# Explicitly pass shape and type
tf.math.accumulate_n([a, b, a], shape=[2, 2], tensor_dtype=tf.int32)
                                                               # [[7,  4],
                                                               #  [6, 14]]
```

#### Args:


* <b>`inputs`</b>: A list of `Tensor` objects, each with same shape and type.
* <b>`shape`</b>: Expected shape of elements of `inputs` (optional). Also controls the
  output shape of this op, which may affect type inference in other ops. A
  value of `None` means "infer the input shape from the shapes in `inputs`".
* <b>`tensor_dtype`</b>: Expected data type of `inputs` (optional). A value of `None`
  means "infer the input dtype from `inputs[0]`".
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of same shape and type as the elements of `inputs`.



#### Raises:


* <b>`ValueError`</b>: If `inputs` don't all have same shape and dtype or the shape
cannot be inferred.

## Compat aliases

* `tf.compat.v1.accumulate_n`
* `tf.compat.v1.math.accumulate_n`
* `tf.compat.v2.math.accumulate_n`

