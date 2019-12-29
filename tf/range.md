<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.range" />
<meta itemprop="path" content="Stable" />
</div>

# tf.range

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/math_ops.py">View source</a>



Creates a sequence of numbers.

``` python
tf.range(limit, delta=1, dtype=None, name='range')
tf.range(start, limit, delta=1, dtype=None, name='range')
```



<!-- Placeholder for "Used in" -->

Creates a sequence of numbers that begins at `start` and extends by
increments of `delta` up to but not including `limit`.

The dtype of the resulting tensor is inferred from the inputs unless
it is provided explicitly.

Like the Python builtin `range`, `start` defaults to 0, so that
`range(n) = range(0, n)`.

#### For example:



```
>>> start = 3
>>> limit = 18
>>> delta = 3
>>> tf.range(start, limit, delta)
<tf.Tensor: shape=(5,), dtype=int32,
numpy=array([ 3,  6,  9, 12, 15], dtype=int32)>
```

```
>>> start = 3
>>> limit = 1
>>> delta = -0.5
>>> tf.range(start, limit, delta)
<tf.Tensor: shape=(4,), dtype=float32,
numpy=array([3. , 2.5, 2. , 1.5], dtype=float32)>
```

```
>>> limit = 5
>>> tf.range(limit)
<tf.Tensor: shape=(5,), dtype=int32,
numpy=array([0, 1, 2, 3, 4], dtype=int32)>
```

#### Args:


* <b>`start`</b>: A 0-D `Tensor` (scalar). Acts as first entry in the range if `limit`
  is not None; otherwise, acts as range limit and first entry defaults to 0.
* <b>`limit`</b>: A 0-D `Tensor` (scalar). Upper limit of sequence, exclusive. If None,
  defaults to the value of `start` while the first entry of the range
  defaults to 0.
* <b>`delta`</b>: A 0-D `Tensor` (scalar). Number that increments `start`. Defaults to
  1.
* <b>`dtype`</b>: The type of the elements of the resulting tensor.
* <b>`name`</b>: A name for the operation. Defaults to "range".


#### Returns:

An 1-D `Tensor` of type `dtype`.




#### Numpy Compatibility
Equivalent to np.arange



## Compat aliases

* `tf.compat.v1.range`
* `tf.compat.v2.range`

