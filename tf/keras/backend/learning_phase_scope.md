<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.learning_phase_scope" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.learning_phase_scope

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Provides a scope within which the learning phase is equal to `value`.

``` python
tf.keras.backend.learning_phase_scope(value)
```



<!-- Placeholder for "Used in" -->

The learning phase gets restored to its original value upon exiting the scope.

#### Arguments:


* <b>`value`</b>: Learning phase value, either 0 or 1 (integers).
       0 = test, 1 = train


#### Yields:

None.



#### Raises:


* <b>`ValueError`</b>: if `value` is neither `0` nor `1`.

## Compat aliases

* `tf.compat.v1.keras.backend.learning_phase_scope`
* `tf.compat.v2.keras.backend.learning_phase_scope`

