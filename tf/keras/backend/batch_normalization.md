<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.batch_normalization" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.batch_normalization

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Applies batch normalization on x given mean, var, beta and gamma.

``` python
tf.keras.backend.batch_normalization(
    x,
    mean,
    var,
    beta,
    gamma,
    axis=-1,
    epsilon=0.001
)
```



<!-- Placeholder for "Used in" -->

I.e. returns:
`output = (x - mean) / (sqrt(var) + epsilon) * gamma + beta`

#### Arguments:


* <b>`x`</b>: Input tensor or variable.
* <b>`mean`</b>: Mean of batch.
* <b>`var`</b>: Variance of batch.
* <b>`beta`</b>: Tensor with which to center the input.
* <b>`gamma`</b>: Tensor by which to scale the input.
* <b>`axis`</b>: Integer, the axis that should be normalized.
    (typically the features axis).
* <b>`epsilon`</b>: Fuzz factor.


#### Returns:

A tensor.


## Compat aliases

* `tf.compat.v1.keras.backend.batch_normalization`
* `tf.compat.v2.keras.backend.batch_normalization`

