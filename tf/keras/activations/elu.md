<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.activations.elu" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.activations.elu

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/activations.py">View source</a>



Exponential linear unit.

``` python
tf.keras.activations.elu(
    x,
    alpha=1.0
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`x`</b>: Input tensor.
* <b>`alpha`</b>: A scalar, slope of negative section.


#### Returns:

The exponential linear activation: `x` if `x > 0` and
  `alpha * (exp(x)-1)` if `x < 0`.



#### Reference:

- [Fast and Accurate Deep Network Learning by Exponential
  Linear Units (ELUs)](https://arxiv.org/abs/1511.07289)


## Compat aliases

* `tf.compat.v1.keras.activations.elu`
* `tf.compat.v2.keras.activations.elu`

