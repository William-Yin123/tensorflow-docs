<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.assert_positive" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.assert_positive

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/check_ops.py">View source</a>



Assert the condition `x > 0` holds element-wise.

``` python
tf.compat.v1.assert_positive(
    x,
    data=None,
    summarize=None,
    message=None,
    name=None
)
```



<!-- Placeholder for "Used in" -->

When running in graph mode, you should add a dependency on this operation
to ensure that it runs. Example of adding a dependency to an operation:

```python
with tf.control_dependencies([tf.debugging.assert_positive(x, y)]):
  output = tf.reduce_sum(x)
```

Positive means, for every element `x[i]` of `x`, we have `x[i] > 0`.
If `x` is empty this is trivially satisfied.

#### Args:


* <b>`x`</b>:  Numeric `Tensor`.
* <b>`data`</b>:  The tensors to print out if the condition is False.  Defaults to
  error message and first few entries of `x`.
* <b>`summarize`</b>: Print this many entries of each tensor.
* <b>`message`</b>: A string to prefix to the default message.
* <b>`name`</b>: A name for this operation (optional).  Defaults to "assert_positive".


#### Returns:

Op that raises `InvalidArgumentError` if `x > 0` is False.




#### Raises:


* <b>`InvalidArgumentError`</b>: if the check can be performed immediately and
  `x > 0` is False. The check can be performed immediately during 
  eager execution or if `x` is statically known.

#### Eager Compatibility
returns None



## Compat aliases

* `tf.compat.v1.debugging.assert_positive`

