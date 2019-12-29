<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.strings.to_number" />
<meta itemprop="path" content="Stable" />
</div>

# tf.strings.to_number

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/string_ops.py">View source</a>



Converts each string in the input Tensor to the specified numeric type.

``` python
tf.strings.to_number(
    input,
    out_type=tf.dtypes.float32,
    name=None
)
```



<!-- Placeholder for "Used in" -->

(Note that int32 overflow results in an error while float overflow
results in a rounded value.)

#### Examples:


>>> tf.strings.to_number("1.55")
<tf.Tensor: id=345, shape=(), dtype=float32, numpy=1.55>
>>> tf.strings.to_number("3", tf.int32)
<tf.Tensor: id=347, shape=(), dtype=int32, numpy=3>

#### Args:


* <b>`input`</b>: A `Tensor` of type `string`.
* <b>`out_type`</b>: An optional <a href="../../tf/dtypes/DType.md"><code>tf.DType</code></a> from: `tf.float32, tf.float64, tf.int32,
  tf.int64`. Defaults to `tf.float32`.
  The numeric type to interpret each string in `string_tensor` as.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `out_type`.


## Compat aliases

* `tf.compat.v2.strings.to_number`

