<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.experimental.preprocessing.PreprocessingLayer" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="adapt"/>
</div>

# tf.keras.layers.experimental.preprocessing.PreprocessingLayer

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/engine/base_preprocessing_layer.py">View source</a>



## Class `PreprocessingLayer`

Base class for PreprocessingLayers.

Inherits From: [`Layer`](../../../../../tf/keras/layers/Layer.md)

<!-- Placeholder for "Used in" -->


<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/engine/base_layer.py">View source</a>

``` python
__init__(
    trainable=True,
    name=None,
    dtype=None,
    dynamic=False,
    **kwargs
)
```






## Methods

<h3 id="adapt"><code>adapt</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/engine/base_preprocessing_layer.py">View source</a>

``` python
adapt(
    data,
    reset_state=True
)
```

Fits the state of the preprocessing layer to the data being passed.


#### Arguments:


* <b>`data`</b>: The data to train on. It can be passed either as a tf.data
  Dataset, or as a numpy array.
* <b>`reset_state`</b>: Optional argument specifying whether to clear the state of
  the layer at the start of the call to `adapt`, or whether to start
  from the existing state. This argument may not be relevant to all
  preprocessing layers: a subclass of PreprocessingLayer may choose to
    throw if 'reset_state' is set to False.





## Compat aliases

* `tf.compat.v1.keras.layers.experimental.preprocessing.PreprocessingLayer`
* `tf.compat.v2.keras.layers.experimental.preprocessing.PreprocessingLayer`

