<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.saved_model.build_tensor_info" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.saved_model.build_tensor_info

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/saved_model/utils_impl.py">View source</a>



Utility function to build TensorInfo proto from a Tensor. (deprecated)

``` python
tf.compat.v1.saved_model.build_tensor_info(tensor)
```



<!-- Placeholder for "Used in" -->

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
This function will only be available through the v1 compatibility library as tf.compat.v1.saved_model.utils.build_tensor_info or tf.compat.v1.saved_model.build_tensor_info.

#### Args:


* <b>`tensor`</b>: Tensor or SparseTensor whose name, dtype and shape are used to
    build the TensorInfo. For SparseTensors, the names of the three
    constituent Tensors are used.


#### Returns:

A TensorInfo protocol buffer constructed based on the supplied argument.



#### Raises:


* <b>`RuntimeError`</b>: If eager execution is enabled.

## Compat aliases

* `tf.compat.v1.saved_model.utils.build_tensor_info`

