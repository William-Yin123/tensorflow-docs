<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.make_ndarray" />
<meta itemprop="path" content="Stable" />
</div>

# tf.make_ndarray

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/framework/tensor_util.py">View source</a>



Create a numpy ndarray from a tensor.

``` python
tf.make_ndarray(tensor)
```



<!-- Placeholder for "Used in" -->

Create a numpy ndarray with the same shape and data as the tensor.

#### For example:



```python
# Tensor a has shape (2,3)
a = tf.constant([[1,2,3],[4,5,6]])
proto_tensor = tf.make_tensor_proto(a)  # convert `tensor a` to a proto tensor
tf.make_ndarray(proto_tensor) # output: array([[1, 2, 3],
#                                              [4, 5, 6]], dtype=int32)
# output has shape (2,3)
```

#### Args:


* <b>`tensor`</b>: A TensorProto.


#### Returns:

A numpy array with the tensor contents.



#### Raises:


* <b>`TypeError`</b>: if tensor has unsupported type.

## Compat aliases

* `tf.compat.v1.make_ndarray`
* `tf.compat.v2.make_ndarray`

