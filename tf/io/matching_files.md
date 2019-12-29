<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.io.matching_files" />
<meta itemprop="path" content="Stable" />
</div>

# tf.io.matching_files

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>



Returns the set of files matching one or more glob patterns.

``` python
tf.io.matching_files(
    pattern,
    name=None
)
```



<!-- Placeholder for "Used in" -->

Note that this routine only supports wildcard characters in the
basename portion of the pattern, not in the directory portion.
Note also that the order of filenames returned is deterministic.

#### Args:


* <b>`pattern`</b>: A `Tensor` of type `string`.
  Shell wildcard pattern(s). Scalar or vector of type string.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `string`.


## Compat aliases

* `tf.compat.v1.io.matching_files`
* `tf.compat.v1.matching_files`
* `tf.compat.v2.io.matching_files`

