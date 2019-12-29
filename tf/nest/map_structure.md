<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.nest.map_structure" />
<meta itemprop="path" content="Stable" />
</div>

# tf.nest.map_structure

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/util/nest.py">View source</a>



Applies `func` to each entry in `structure` and returns a new structure.

``` python
tf.nest.map_structure(
    func,
    *structure,
    **kwargs
)
```



<!-- Placeholder for "Used in" -->

Applies `func(x[0], x[1], ...)` where x[i] is an entry in
`structure[i]`.  All structures in `structure` must have the same arity,
and the return value will contain results with the same structure layout.

#### Args:


* <b>`func`</b>: A callable that accepts as many arguments as there are structures.
* <b>`*structure`</b>: scalar, or tuple or list of constructed scalars and/or other
  tuples/lists, or scalars.  Note: numpy arrays are considered as scalars.
* <b>`**kwargs`</b>: Valid keyword args are:

  * `check_types`: If set to `True` (default) the types of
    iterables within the structures have to be same (e.g.
    `map_structure(func, [1], (1,))` raises a `TypeError`
    exception). To allow this set this argument to `False`.
    Note that namedtuples with identical name and fields are always
    considered to have the same shallow structure.
  * `expand_composites`: If set to `True`, then composite tensors such
    as <a href="../../tf/sparse/SparseTensor.md"><code>tf.SparseTensor</code></a> and <a href="../../tf/RaggedTensor.md"><code>tf.RaggedTensor</code></a> are expanded into their
    component tensors.  If `False` (the default), then composite tensors
    are not expanded.


#### Returns:

A new structure with the same arity as `structure`, whose values correspond
to `func(x[0], x[1], ...)` where `x[i]` is a value in the corresponding
location in `structure[i]`. If there are different sequence types and
`check_types` is `False` the sequence types of the first structure will be
used.



#### Raises:


* <b>`TypeError`</b>: If `func` is not callable or if the structures do not match
  each other by depth tree.
* <b>`ValueError`</b>: If no structure is provided or if the structures do not match
  each other by type.
* <b>`ValueError`</b>: If wrong keyword arguments are provided.

## Compat aliases

* `tf.compat.v1.nest.map_structure`
* `tf.compat.v2.nest.map_structure`
