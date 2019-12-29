<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.RepeatVector" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
</div>

# tf.keras.layers.RepeatVector

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/core.py">View source</a>



## Class `RepeatVector`

Repeats the input n times.

Inherits From: [`Layer`](../../../tf/keras/layers/Layer.md)

<!-- Placeholder for "Used in" -->


#### Example:



```python
model = Sequential()
model.add(Dense(32, input_dim=32))
# now: model.output_shape == (None, 32)
# note: `None` is the batch dimension

model.add(RepeatVector(3))
# now: model.output_shape == (None, 3, 32)
```

#### Arguments:


* <b>`n`</b>: Integer, repetition factor.


#### Input shape:

2D tensor of shape `(num_samples, features)`.



#### Output shape:

3D tensor of shape `(num_samples, n, features)`.


<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/core.py">View source</a>

``` python
__init__(
    n,
    **kwargs
)
```








## Compat aliases

* `tf.compat.v1.keras.layers.RepeatVector`
* `tf.compat.v2.keras.layers.RepeatVector`

