<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.normalize_batch_in_training" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.normalize_batch_in_training

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Computes mean and std for batch then apply batch_normalization on batch.

``` python
tf.keras.backend.normalize_batch_in_training(
    x,
    gamma,
    beta,
    reduction_axes,
    epsilon=0.001
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`x`</b>: Input tensor or variable.
* <b>`gamma`</b>: Tensor by which to scale the input.
* <b>`beta`</b>: Tensor with which to center the input.
* <b>`reduction_axes`</b>: iterable of integers,
    axes over which to normalize.
* <b>`epsilon`</b>: Fuzz factor.


#### Returns:

A tuple length of 3, `(normalized_tensor, mean, variance)`.


## Compat aliases

* `tf.compat.v1.keras.backend.normalize_batch_in_training`
* `tf.compat.v2.keras.backend.normalize_batch_in_training`

