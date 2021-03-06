<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.foldr" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.foldr

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Reduce elems using fn to combine them from right to left.

``` python
tf.keras.backend.foldr(
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
* <b>`initializer`</b>: The first value used (`elems[-1]` in case of None)
* <b>`name`</b>: A string name for the foldr node in the graph


#### Returns:

Same type and shape as initializer


## Compat aliases

* `tf.compat.v1.keras.backend.foldr`
* `tf.compat.v2.keras.backend.foldr`

