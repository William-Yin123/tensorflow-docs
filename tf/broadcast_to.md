<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.broadcast_to" />
<meta itemprop="path" content="Stable" />
</div>

# tf.broadcast_to

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>



Broadcast an array for a compatible shape.

``` python
tf.broadcast_to(
    input,
    shape,
    name=None
)
```



<!-- Placeholder for "Used in" -->

Broadcasting is the process of making arrays to have compatible shapes
for arithmetic operations. Two shapes are compatible if for each
dimension pair they are either equal or one of them is one. When trying
to broadcast a Tensor to a shape, it starts with the trailing dimensions,
and works its way forward.

For example,

```
>>> x = tf.constant([1, 2, 3])
>>> y = tf.broadcast_to(x, [3, 3])
>>> print(y)
tf.Tensor(
    [[1 2 3]
     [1 2 3]
     [1 2 3]], shape=(3, 3), dtype=int32)
```

In the above example, the input Tensor with the shape of `[1, 3]`
is broadcasted to output Tensor with shape of `[3, 3]`.

#### Args:


* <b>`input`</b>: A `Tensor`. A Tensor to broadcast.
* <b>`shape`</b>: A `Tensor`. Must be one of the following types: `int32`, `int64`.
  An 1-D `int` Tensor. The shape of the desired output.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `input`.


## Compat aliases

* `tf.compat.v1.broadcast_to`
* `tf.compat.v2.broadcast_to`

