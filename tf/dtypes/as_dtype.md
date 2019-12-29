<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.dtypes.as_dtype" />
<meta itemprop="path" content="Stable" />
</div>

# tf.dtypes.as_dtype

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/framework/dtypes.py">View source</a>



Converts the given `type_value` to a `DType`.

**Aliases**: `tf.as_dtype`

``` python
tf.dtypes.as_dtype(type_value)
```



<!-- Placeholder for "Used in" -->


#### Args:


* <b>`type_value`</b>: A value that can be converted to a <a href="../../tf/dtypes/DType.md"><code>tf.DType</code></a> object. This may
  currently be a <a href="../../tf/dtypes/DType.md"><code>tf.DType</code></a> object, a [`DataType`
  enum](https://www.tensorflow.org/code/tensorflow/core/framework/types.proto),
    a string type name, or a `numpy.dtype`.


#### Returns:

A `DType` corresponding to `type_value`.



#### Raises:


* <b>`TypeError`</b>: If `type_value` cannot be converted to a `DType`.

## Compat aliases

* `tf.compat.v1.as_dtype`
* `tf.compat.v1.dtypes.as_dtype`
* `tf.compat.v2.as_dtype`
* `tf.compat.v2.dtypes.as_dtype`
