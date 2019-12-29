<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.assert_equal" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.assert_equal

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/check_ops.py">View source</a>



Assert the condition `x == y` holds element-wise.

``` python
tf.compat.v1.assert_equal(
    x,
    y,
    data=None,
    summarize=None,
    message=None,
    name=None
)
```



<!-- Placeholder for "Used in" -->

This condition holds if for every pair of (possibly broadcast) elements
`x[i]`, `y[i]`, we have `x[i] == y[i]`.
If both `x` and `y` are empty, this is trivially satisfied.

When running in graph mode, you should add a dependency on this operation
to ensure that it runs. Example of adding a dependency to an operation:

```python
with tf.control_dependencies([tf.compat.v1.assert_equal(x, y)]):
  output = tf.reduce_sum(x)
```

#### Args:


* <b>`x`</b>:  Numeric `Tensor`.
* <b>`y`</b>:  Numeric `Tensor`, same dtype as and broadcastable to `x`.
* <b>`data`</b>:  The tensors to print out if the condition is False.  Defaults to
  error message and first few entries of `x`, `y`.
* <b>`summarize`</b>: Print this many entries of each tensor.
* <b>`message`</b>: A string to prefix to the default message.
* <b>`name`</b>: A name for this operation (optional).  Defaults to "assert_equal".


#### Returns:

Op that raises `InvalidArgumentError` if `x == y` is False.




#### Raises:


* <b>`InvalidArgumentError`</b>: if the check can be performed immediately and
  `x == y` is False. The check can be performed immediately during 
  eager execution or if `x` and `y` are statically known.

#### Eager Compatibility
returns None



## Compat aliases

* `tf.compat.v1.debugging.assert_equal`

