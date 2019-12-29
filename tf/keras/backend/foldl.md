<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.foldl" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.foldl

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Reduce elems using fn to combine them from left to right.

``` python
tf.keras.backend.foldl(
    fn,
    elems,
    initializer=None,
    name=None
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`fn`</b>: Callable that will be called upon each element in elems and an
    accumulator, for instance `lambda acc, x: acc + x`
* <b>`elems`</b>: tensor
* <b>`initializer`</b>: The first value used (`elems[0]` in case of None)
* <b>`name`</b>: A string name for the foldl node in the graph


#### Returns:

Tensor with same type and shape as `initializer`.


## Compat aliases

* `tf.compat.v1.keras.backend.foldl`
* `tf.compat.v2.keras.backend.foldl`
