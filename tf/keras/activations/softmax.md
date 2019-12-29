<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.activations.softmax" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.activations.softmax

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/activations.py">View source</a>



Softmax converts a real vector to a vector of categorical probabilities.

``` python
tf.keras.activations.softmax(
    x,
    axis=-1
)
```



<!-- Placeholder for "Used in" -->

The elements of the output vector are in range (0, 1) and sum to 1.

Each vector is handled independently. The `axis` argument sets which axis
of the input the function is applied along.

Softmax is often used as the activation for the last
layer of a classification network because the result could be interpreted as
a probability distribution.

The softmax of each vector x is calculated by `exp(x)/tf.reduce_sum(exp(x))`.
The input values in are the log-odds of the resulting probability.

#### Arguments:


* <b>`x`</b>: Input tensor.
* <b>`axis`</b>: Integer, axis along which the softmax normalization is applied.


#### Returns:

Tensor, output of softmax transformation (all values are non-negative
  and sum to 1).



#### Raises:


* <b>`ValueError`</b>: In case `dim(x) == 1`.

## Compat aliases

* `tf.compat.v1.keras.activations.softmax`
* `tf.compat.v2.keras.activations.softmax`

