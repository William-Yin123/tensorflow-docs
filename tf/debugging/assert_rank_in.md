<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.debugging.assert_rank_in" />
<meta itemprop="path" content="Stable" />
</div>

# tf.debugging.assert_rank_in

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/check_ops.py">View source</a>



Assert that `x` has a rank in `ranks`.

``` python
tf.debugging.assert_rank_in(
    x,
    ranks,
    message=None,
    name=None
)
```



<!-- Placeholder for "Used in" -->

This Op checks that the rank of `x` is in `ranks`.

If `x` has a different rank, `message`, as well as the shape of `x` are
printed, and `InvalidArgumentError` is raised.

#### Args:


* <b>`x`</b>: `Tensor`.
* <b>`ranks`</b>: `Iterable` of scalar `Tensor` objects.
* <b>`message`</b>: A string to prefix to the default message.
* <b>`name`</b>: A name for this operation (optional). Defaults to "assert_rank_in".


#### Returns:

Op raising `InvalidArgumentError` unless rank of `x` is in `ranks`.
If static checks determine `x` has matching rank, a `no_op` is returned.
This can be used with <a href="../../tf/control_dependencies.md"><code>tf.control_dependencies</code></a> inside of <a href="../../tf/function.md"><code>tf.function</code></a>s
to block followup computation until the check has executed.




#### Raises:


* <b>`InvalidArgumentError`</b>: `x` does not have rank in `ranks`, but the rank cannot
  be statically determined.
* <b>`ValueError`</b>: If static checks determine `x` has mismatched rank.

#### Eager Compatibility
returns None



## Compat aliases

* `tf.compat.v2.debugging.assert_rank_in`

