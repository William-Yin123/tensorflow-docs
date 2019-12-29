<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.set_learning_phase" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.set_learning_phase

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Sets the learning phase to a fixed value.

``` python
tf.keras.backend.set_learning_phase(value)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`value`</b>: Learning phase value, either 0 or 1 (integers).
       0 = test, 1 = train


#### Raises:


* <b>`ValueError`</b>: if `value` is neither `0` nor `1`.

## Compat aliases

* `tf.compat.v1.keras.backend.set_learning_phase`
* `tf.compat.v2.keras.backend.set_learning_phase`

