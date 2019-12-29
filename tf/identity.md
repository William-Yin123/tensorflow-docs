<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.identity" />
<meta itemprop="path" content="Stable" />
</div>

# tf.identity

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/array_ops.py">View source</a>



Return a Tensor with the same shape and contents as input.

``` python
tf.identity(
    input,
    name=None
)
```



<!-- Placeholder for "Used in" -->

The return value is not the same Tensor as the original, but contains the same
values.  This operation is fast when used on the same device.

#### For example:



```
>>> a = tf.constant([0.78])
>>> a_identity = tf.identity(a)
>>> a.numpy()
array([0.78], dtype=float32)
>>> a_identity.numpy()
array([0.78], dtype=float32)
```

Calling <a href="../tf/identity.md"><code>tf.identity</code></a> on a variable will make a Tensor that represents the
value of that variable at the time it is called. This is equivalent to calling
`<variable>.read_value()`.

```
>>> a = tf.Variable(5)
>>> a_identity = tf.identity(a)
>>> a.assign_add(1)
<tf.Variable ... shape=() dtype=int32, numpy=6>
>>> a.numpy()
6
>>> a_identity.numpy()
5
```

#### Args:


* <b>`input`</b>: A `Tensor`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `input`.


## Compat aliases

* `tf.compat.v1.identity`
* `tf.compat.v2.identity`

