<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.get_static_value" />
<meta itemprop="path" content="Stable" />
</div>

# tf.get_static_value

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/framework/tensor_util.py">View source</a>



Returns the constant value of the given tensor, if efficiently calculable.

``` python
tf.get_static_value(
    tensor,
    partial=False
)
```



<!-- Placeholder for "Used in" -->

This function attempts to partially evaluate the given tensor, and
returns its value as a numpy ndarray if this succeeds.

Compatibility(V1): If `constant_value(tensor)` returns a non-`None` result, it
will no longer be possible to feed a different value for `tensor`. This allows
the result of this function to influence the graph that is constructed, and
permits static shape optimizations.

#### Args:


* <b>`tensor`</b>: The Tensor to be evaluated.
* <b>`partial`</b>: If True, the returned numpy array is allowed to have partially
  evaluated values. Values that can't be evaluated will be None.


#### Returns:

A numpy ndarray containing the constant value of the given `tensor`,
or None if it cannot be calculated.



#### Raises:


* <b>`TypeError`</b>: if tensor is not an ops.Tensor.

## Compat aliases

* `tf.compat.v1.get_static_value`
* `tf.compat.v2.get_static_value`

