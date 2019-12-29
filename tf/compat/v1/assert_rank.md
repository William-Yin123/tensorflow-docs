<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.assert_rank" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.assert_rank

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/check_ops.py">View source</a>



Assert `x` has rank equal to `rank`.

``` python
tf.compat.v1.assert_rank(
    x,
    rank,
    data=None,
    summarize=None,
    message=None,
    name=None
)
```



<!-- Placeholder for "Used in" -->

Example of adding a dependency to an operation:

```python
with tf.control_dependencies([tf.compat.v1.assert_rank(x, 2)]):
  output = tf.reduce_sum(x)
```

#### Args:


* <b>`x`</b>:  Numeric `Tensor`.
* <b>`rank`</b>:  Scalar integer `Tensor`.
* <b>`data`</b>:  The tensors to print out if the condition is False.  Defaults to
  error message and the shape of `x`.
* <b>`summarize`</b>: Print this many entries of each tensor.
* <b>`message`</b>: A string to prefix to the default message.
* <b>`name`</b>: A name for this operation (optional).  Defaults to "assert_rank".


#### Returns:

Op raising `InvalidArgumentError` unless `x` has specified rank.
If static checks determine `x` has correct rank, a `no_op` is returned.



#### Raises:


* <b>`ValueError`</b>:  If static checks determine `x` has wrong rank.

## Compat aliases

* `tf.compat.v1.debugging.assert_rank`

