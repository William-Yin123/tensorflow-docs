<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.sobol_sample" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.sobol_sample

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/math_ops.py">View source</a>



Generates points from the Sobol sequence.

``` python
tf.math.sobol_sample(
    dim,
    num_results,
    skip=0,
    dtype=None,
    name=None
)
```



<!-- Placeholder for "Used in" -->

Creates a Sobol sequence with `num_results` samples. Each sample has dimension
`dim`. Skips the first `skip` samples.

#### Args:


* <b>`dim`</b>: Positive scalar `Tensor` representing each sample's dimension.
* <b>`num_results`</b>: Positive scalar `Tensor` of dtype int32. The number of Sobol
    points to return in the output.
* <b>`skip`</b>: (Optional) Positive scalar `Tensor` of dtype int32. The number of
    initial points of the Sobol sequence to skip. Default value is 0.
* <b>`dtype`</b>: (Optional) The dtype of the sample. One of: `float32` or `float64`.
    Default value is determined by the C++ kernel.
* <b>`name`</b>: (Optional) Python `str` name prefixed to ops created by this function.


#### Returns:

`Tensor` of samples from Sobol sequence with `shape` [num_results, dim].


## Compat aliases

* `tf.compat.v1.math.sobol_sample`
* `tf.compat.v2.math.sobol_sample`

