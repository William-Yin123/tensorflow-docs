<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.nn.weighted_moments" />
<meta itemprop="path" content="Stable" />
</div>

# tf.nn.weighted_moments

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/nn_impl.py">View source</a>



Returns the frequency-weighted mean and variance of `x`.

``` python
tf.nn.weighted_moments(
    x,
    axes,
    frequency_weights,
    keepdims=False,
    name=None
)
```



<!-- Placeholder for "Used in" -->


#### Args:


* <b>`x`</b>: A tensor.
* <b>`axes`</b>: 1-d tensor of int32 values; these are the axes along which
  to compute mean and variance.
* <b>`frequency_weights`</b>: A tensor of positive weights which can be
  broadcast with x.
* <b>`keepdims`</b>: Produce moments with the same dimensionality as the input.
* <b>`name`</b>: Name used to scope the operation.


#### Returns:

Two tensors: `weighted_mean` and `weighted_variance`.


## Compat aliases

* `tf.compat.v2.nn.weighted_moments`

