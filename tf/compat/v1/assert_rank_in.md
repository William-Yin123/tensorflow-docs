<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.assert_rank_in" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.assert_rank_in

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/check_ops.py">View source</a>



Assert `x` has rank in `ranks`.

``` python
tf.compat.v1.assert_rank_in(
    x,
    ranks,
    data=None,
    summarize=None,
    message=None,
    name=None
)
```



<!-- Placeholder for "Used in" -->

Example of adding a dependency to an operation:

```python
with tf.control_dependencies([tf.compat.v1.assert_rank_in(x, (2, 4))]):
  output = tf.reduce_sum(x)
```

#### Args:


* <b>`x`</b>:  Numeric `Tensor`.
* <b>`ranks`</b>:  Iterable of scalar `Tensor` objects.
* <b>`data`</b>:  The tensors to print out if the condition is False.  Defaults to
  error message and first few entries of `x`.
* <b>`summarize`</b>: Print this many entries of each tensor.
* <b>`message`</b>: A string to prefix to the default message.
* <b>`name`</b>: A name for this operation (optional).
  Defaults to "assert_rank_in".


#### Returns:

Op raising `InvalidArgumentError` unless rank of `x` is in `ranks`.
If static checks determine `x` has matching rank, a `no_op` is returned.



#### Raises:


* <b>`ValueError`</b>:  If static checks determine `x` has mismatched rank.

## Compat aliases

* `tf.compat.v1.debugging.assert_rank_in`

