<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.map_fn" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.map_fn

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Map the function fn over the elements elems and return the outputs.

``` python
tf.keras.backend.map_fn(
    fn,
    elems,
    name=None,
    dtype=None
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`fn`</b>: Callable that will be called upon each element in elems
* <b>`elems`</b>: tensor
* <b>`name`</b>: A string name for the map node in the graph
* <b>`dtype`</b>: Output data type.


#### Returns:

Tensor with dtype `dtype`.


## Compat aliases

* `tf.compat.v1.keras.backend.map_fn`
* `tf.compat.v2.keras.backend.map_fn`

