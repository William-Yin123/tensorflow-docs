<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.in_test_phase" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.in_test_phase

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Selects `x` in test phase, and `alt` otherwise.

``` python
tf.keras.backend.in_test_phase(
    x,
    alt,
    training=None
)
```



<!-- Placeholder for "Used in" -->

Note that `alt` should have the *same shape* as `x`.

#### Arguments:


* <b>`x`</b>: What to return in test phase
    (tensor or callable that returns a tensor).
* <b>`alt`</b>: What to return otherwise
    (tensor or callable that returns a tensor).
* <b>`training`</b>: Optional scalar tensor
    (or Python boolean, or Python integer)
    specifying the learning phase.


#### Returns:

Either `x` or `alt` based on `K.learning_phase`.


## Compat aliases

* `tf.compat.v1.keras.backend.in_test_phase`
* `tf.compat.v2.keras.backend.in_test_phase`

