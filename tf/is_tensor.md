<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.is_tensor" />
<meta itemprop="path" content="Stable" />
</div>

# tf.is_tensor

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/framework/tensor_util.py">View source</a>



Checks whether `x` is a tensor or "tensor-like".

``` python
tf.is_tensor(x)
```



<!-- Placeholder for "Used in" -->

If `is_tensor(x)` returns `True`, it is safe to assume that `x` is a tensor or
can be converted to a tensor using `ops.convert_to_tensor(x)`.

#### Args:


* <b>`x`</b>: A python object to check.


#### Returns:

`True` if `x` is a tensor or "tensor-like", `False` if not.


## Compat aliases

* `tf.compat.v1.is_tensor`
* `tf.compat.v2.is_tensor`

