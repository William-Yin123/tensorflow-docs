<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.debugging.assert_all_finite" />
<meta itemprop="path" content="Stable" />
</div>

# tf.debugging.assert_all_finite

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/numerics.py">View source</a>



Assert that the tensor does not contain any NaN's or Inf's.

``` python
tf.debugging.assert_all_finite(
    x,
    message,
    name=None
)
```



<!-- Placeholder for "Used in" -->


#### Args:


* <b>`x`</b>: Tensor to check.
* <b>`message`</b>: Message to log on failure.
* <b>`name`</b>: A name for this operation (optional).


#### Returns:

Same tensor as `x`.


## Compat aliases

* `tf.compat.v2.debugging.assert_all_finite`

