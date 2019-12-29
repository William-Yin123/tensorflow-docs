<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.set_epsilon" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.set_epsilon

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend_config.py">View source</a>



Sets the value of the fuzz factor used in numeric expressions.

``` python
tf.keras.backend.set_epsilon(value)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`value`</b>: float. New value of epsilon.
Example: ```python from keras import backend as K K.epsilon() >>> 1e-07
  K.set_epsilon(1e-05) K.epsilon() >>> 1e-05 ```

## Compat aliases

* `tf.compat.v1.keras.backend.set_epsilon`
* `tf.compat.v2.keras.backend.set_epsilon`

