<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.foldl" />
<meta itemprop="path" content="Stable" />
</div>

# tf.foldl

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/functional_ops.py">View source</a>



foldl on the list of tensors unpacked from `elems` on dimension 0. (deprecated argument values)

``` python
tf.foldl(
    fn,
    elems,
    initializer=None,
    parallel_iterations=10,
    back_prop=True,
    swap_memory=False,
    name=None
)
```



<!-- Placeholder for "Used in" -->

Warning: SOME ARGUMENT VALUES ARE DEPRECATED: `(back_prop=False)`. They will be removed in a future version.
Instructions for updating:
back_prop=False is deprecated. Consider using tf.stop_gradient instead.
Instead of:
results = tf.foldl(fn, elems, back_prop=False)
Use:
results = tf.nest.map_structure(tf.stop_gradient, tf.foldl(fn, elems))

This foldl operator repeatedly applies the callable `fn` to a sequence
of elements from first to last. The elements are made of the tensors
unpacked from `elems` on dimension 0. The callable fn takes two tensors as
arguments. The first argument is the accumulated value computed from the
preceding invocation of fn, and the second is the value at the current
position of `elems`. If `initializer` is None, `elems` must contain at least
one element, and its first element is used as the initializer.

Suppose that `elems` is unpacked into `values`, a list of tensors. The shape
of the result tensor is fn(initializer, values[0]).shape`.

This method also allows multi-arity `elems` and output of `fn`.  If `elems`
is a (possibly nested) list or tuple of tensors, then each of these tensors
must have a matching first (unpack) dimension.  The signature of `fn` may
match the structure of `elems`.  That is, if `elems` is
`(t1, [t2, t3, [t4, t5]])`, then an appropriate signature for `fn` is:
`fn = lambda (t1, [t2, t3, [t4, t5]]):`.

#### Args:


* <b>`fn`</b>: The callable to be performed.
* <b>`elems`</b>: A tensor or (possibly nested) sequence of tensors, each of which will
  be unpacked along their first dimension.  The nested sequence of the
  resulting slices will be the first argument to `fn`.
* <b>`initializer`</b>: (optional) A tensor or (possibly nested) sequence of tensors,
  as the initial value for the accumulator.
* <b>`parallel_iterations`</b>: (optional) The number of iterations allowed to run in
  parallel.
* <b>`back_prop`</b>: (optional) Deprecated. False disables support for back
  propagation. Prefer using <a href="../tf/stop_gradient.md"><code>tf.stop_gradient</code></a> instead.
* <b>`swap_memory`</b>: (optional) True enables GPU-CPU memory swapping.
* <b>`name`</b>: (optional) Name prefix for the returned tensors.


#### Returns:

A tensor or (possibly nested) sequence of tensors, resulting from applying
`fn` consecutively to the list of tensors unpacked from `elems`, from first
to last.



#### Raises:


* <b>`TypeError`</b>: if `fn` is not callable.


#### Example:

```python
elems = tf.constant([1, 2, 3, 4, 5, 6])
sum = foldl(lambda a, x: a + x, elems)
# sum == 21
```


## Compat aliases

* `tf.compat.v2.foldl`

