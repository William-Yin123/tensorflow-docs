<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.reduce_mean" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.reduce_mean

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/math_ops.py">View source</a>



Computes the mean of elements across dimensions of a tensor.

``` python
tf.compat.v1.reduce_mean(
    input_tensor,
    axis=None,
    keepdims=None,
    name=None,
    reduction_indices=None,
    keep_dims=None
)
```



<!-- Placeholder for "Used in" -->

Reduces `input_tensor` along the dimensions given in `axis` by computing the
mean of elements across the dimensions in `axis`.
Unless `keepdims` is true, the rank of the tensor is reduced by 1 for each
entry in `axis`. If `keepdims` is true, the reduced dimensions
are retained with length 1.

If `axis` is None, all dimensions are reduced, and a tensor with a single
element is returned.

#### For example:



```
>>> x = tf.constant([[1., 1.], [2., 2.]])
>>> tf.reduce_mean(x)
<tf.Tensor: shape=(), dtype=float32, numpy=1.5>
>>> tf.reduce_mean(x, 0)
<tf.Tensor: shape=(2,), dtype=float32, numpy=array([1.5, 1.5], dtype=float32)>
>>> tf.reduce_mean(x, 1)
<tf.Tensor: shape=(2,), dtype=float32, numpy=array([1., 2.], dtype=float32)>
```

#### Args:


* <b>`input_tensor`</b>: The tensor to reduce. Should have numeric type.
* <b>`axis`</b>: The dimensions to reduce. If `None` (the default), reduces all
  dimensions. Must be in the range `[-rank(input_tensor),
  rank(input_tensor))`.
* <b>`keepdims`</b>: If true, retains reduced dimensions with length 1.
* <b>`name`</b>: A name for the operation (optional).
* <b>`reduction_indices`</b>: The old (deprecated) name for axis.
* <b>`keep_dims`</b>: Deprecated alias for `keepdims`.


#### Returns:

The reduced tensor.




#### Numpy Compatibility
Equivalent to np.mean

Please note that `np.mean` has a `dtype` parameter that could be used to
specify the output type. By default this is `dtype=float64`. On the other
hand, <a href="../../../tf/math/reduce_mean.md"><code>tf.reduce_mean</code></a> has an aggressive type inference from `input_tensor`,
for example:

```
>>> x = tf.constant([1, 0, 1, 0])
>>> tf.reduce_mean(x)
<tf.Tensor: shape=(), dtype=int32, numpy=0>
>>> y = tf.constant([1., 0., 1., 0.])
>>> tf.reduce_mean(y)
<tf.Tensor: shape=(), dtype=float32, numpy=0.5>
```




## Compat aliases

* `tf.compat.v1.math.reduce_mean`

