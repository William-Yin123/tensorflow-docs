<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.hard_sigmoid" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.hard_sigmoid

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Segment-wise linear approximation of sigmoid.

``` python
tf.keras.backend.hard_sigmoid(x)
```



<!-- Placeholder for "Used in" -->

Faster than sigmoid.
Returns `0.` if `x < -2.5`, `1.` if `x > 2.5`.
In `-2.5 <= x <= 2.5`, returns `0.2 * x + 0.5`.

#### Arguments:


* <b>`x`</b>: A tensor or variable.


#### Returns:

A tensor.


## Compat aliases

* `tf.compat.v1.keras.backend.hard_sigmoid`
* `tf.compat.v2.keras.backend.hard_sigmoid`

