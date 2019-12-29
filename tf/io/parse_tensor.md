<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.io.parse_tensor" />
<meta itemprop="path" content="Stable" />
</div>

# tf.io.parse_tensor

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>



Transforms a serialized tensorflow.TensorProto proto into a Tensor.

``` python
tf.io.parse_tensor(
    serialized,
    out_type,
    name=None
)
```



<!-- Placeholder for "Used in" -->


#### Args:


* <b>`serialized`</b>: A `Tensor` of type `string`.
  A scalar string containing a serialized TensorProto proto.
* <b>`out_type`</b>: A <a href="../../tf/dtypes/DType.md"><code>tf.DType</code></a>.
  The type of the serialized tensor.  The provided type must match the
  type of the serialized tensor and no implicit conversion will take place.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `out_type`.


## Compat aliases

* `tf.compat.v1.io.parse_tensor`
* `tf.compat.v1.parse_tensor`
* `tf.compat.v2.io.parse_tensor`

