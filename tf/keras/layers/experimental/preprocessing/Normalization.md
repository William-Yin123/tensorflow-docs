<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.experimental.preprocessing.Normalization" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="adapt"/>
</div>

# tf.keras.layers.experimental.preprocessing.Normalization

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/preprocessing/normalization.py">View source</a>



## Class `Normalization`

Feature-wise normalization of the data.



<!-- Placeholder for "Used in" -->

This layer will coerce its inputs into a normal distribution centered around
0 with standard deviation 1. It accomplishes this by precomputing the mean and
variance of the data, and calling (input-mean)/sqrt(var) at runtime.

What happens in `adapt`: Compute mean and variance of the data and store them
  as the layer's weights. `adapt` should be called before `fit`, `evaluate`,
  or `predict`.

#### Attributes:


* <b>`axis`</b>: Integer or tuple of integers, the axis or axes that should be
  normalized (typically the features axis). We will normalize each element
  in the specified axis. The default is '-1' (the innermost axis); 0 (the
  batch axis) is not allowed.

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/preprocessing/normalization.py">View source</a>

``` python
__init__(
    axis=-1,
    dtype=None,
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


* <b>`data`</b>: The data to train on. It can be passed either as a tf.data Dataset,
  or as a numpy array.
* <b>`reset_state`</b>: Optional argument specifying whether to clear the state of
  the layer at the start of the call to `adapt`, or whether to start from
  the existing state. Subclasses may choose to throw if reset_state is set
  to 'False'.





## Compat aliases

* `tf.compat.v2.keras.layers.experimental.preprocessing.Normalization`

