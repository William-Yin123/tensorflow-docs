<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.get_session_tensor" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.get_session_tensor

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/session_ops.py">View source</a>



Get the tensor of type `dtype` by feeding a tensor handle.

``` python
tf.compat.v1.get_session_tensor(
    handle,
    dtype,
    name=None
)
```



<!-- Placeholder for "Used in" -->

This is EXPERIMENTAL and subject to change.

Get the value of the tensor from a tensor handle. The tensor
is produced in a previous run() and stored in the state of the
session.

#### Args:


* <b>`handle`</b>: The string representation of a persistent tensor handle.
* <b>`dtype`</b>: The type of the output tensor.
* <b>`name`</b>: Optional name prefix for the return tensor.


#### Returns:

A pair of tensors. The first is a placeholder for feeding a
tensor handle and the second is the tensor in the session state
keyed by the tensor handle.



#### Example:



```python
c = tf.multiply(a, b)
h = tf.compat.v1.get_session_handle(c)
h = sess.run(h)

p, a = tf.compat.v1.get_session_tensor(h.handle, tf.float32)
b = tf.multiply(a, 10)
c = sess.run(b, feed_dict={p: h.handle})
```
