<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.ragged.boolean_mask" />
<meta itemprop="path" content="Stable" />
</div>

# tf.ragged.boolean_mask

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/ragged/ragged_array_ops.py">View source</a>



Applies a boolean mask to `data` without flattening the mask dimensions.

``` python
tf.ragged.boolean_mask(
    data,
    mask,
    name=None
)
```



<!-- Placeholder for "Used in" -->

Returns a potentially ragged tensor that is formed by retaining the elements
in `data` where the corresponding value in `mask` is `True`.

* `output[a1...aA, i, b1...bB] = data[a1...aA, j, b1...bB]`

   Where `j` is the `i`th `True` entry of `mask[a1...aA]`.

Note that `output` preserves the mask dimensions `a1...aA`; this differs
from <a href="../../tf/boolean_mask.md"><code>tf.boolean_mask</code></a>, which flattens those dimensions.

#### Args:


* <b>`data`</b>: A potentially ragged tensor.
* <b>`mask`</b>: A potentially ragged boolean tensor.  `mask`'s shape must be a prefix
  of `data`'s shape.  `rank(mask)` must be known statically.
* <b>`name`</b>: A name prefix for the returned tensor (optional).


#### Returns:

A potentially ragged tensor that is formed by retaining the elements in
`data` where the corresponding value in `mask` is `True`.

* `rank(output) = rank(data)`.
* `output.ragged_rank = max(data.ragged_rank, rank(mask) - 1)`.



#### Raises:


* <b>`ValueError`</b>: if `rank(mask)` is not known statically; or if `mask.shape` is
  not a prefix of `data.shape`.

#### Examples:

```
>>> # Aliases for True & False so data and mask line up.
>>> T, F = (True, False)
```

```
>>> tf.ragged.boolean_mask(  # Mask a 2D Tensor.
...     data=[[1, 2, 3], [4, 5, 6], [7, 8, 9]],
...     mask=[[T, F, T], [F, F, F], [T, F, F]]).to_list()
[[1, 3], [], [7]]
```

```
>>> tf.ragged.boolean_mask(  # Mask a 2D RaggedTensor.
...     tf.ragged.constant([[1, 2, 3], [4], [5, 6]]),
...     tf.ragged.constant([[F, F, T], [F], [T, T]])).to_list()
[[3], [], [5, 6]]
```

```
>>> tf.ragged.boolean_mask(  # Mask rows of a 2D RaggedTensor.
...     tf.ragged.constant([[1, 2, 3], [4], [5, 6]]),
...     tf.ragged.constant([True, False, True])).to_list()
[[1, 2, 3], [5, 6]]
```

## Compat aliases

* `tf.compat.v1.ragged.boolean_mask`
* `tf.compat.v2.ragged.boolean_mask`

