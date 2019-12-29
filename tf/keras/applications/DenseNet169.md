<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.applications.DenseNet169" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.applications.DenseNet169

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/applications/densenet.py">View source</a>



Instantiates the Densenet169 architecture.

**Aliases**: `tf.keras.applications.densenet.DenseNet169`

``` python
tf.keras.applications.DenseNet169(
    include_top=True,
    weights='imagenet',
    input_tensor=None,
    input_shape=None,
    pooling=None,
    classes=1000
)
```



<!-- Placeholder for "Used in" -->

Optionally loads weights pre-trained on ImageNet.
Note that the data format convention used by the model is
the one specified in your Keras config at `~/.keras/keras.json`.

#### Arguments:


* <b>`include_top`</b>: whether to include the fully-connected
  layer at the top of the network.
* <b>`weights`</b>: one of `None` (random initialization),
  'imagenet' (pre-training on ImageNet),
  or the path to the weights file to be loaded.
* <b>`input_tensor`</b>: optional Keras tensor (i.e. output of <a href="../../../tf/keras/Input.md"><code>layers.Input()</code></a>)
  to use as image input for the model.
* <b>`input_shape`</b>: optional shape tuple, only to be specified
  if `include_top` is False (otherwise the input shape
  has to be `(224, 224, 3)` (with `'channels_last'` data format)
  or `(3, 224, 224)` (with `'channels_first'` data format).
  It should have exactly 3 inputs channels,
  and width and height should be no smaller than 32.
  E.g. `(200, 200, 3)` would be one valid value.
* <b>`pooling`</b>: Optional pooling mode for feature extraction
  when `include_top` is `False`.
  - `None` means that the output of the model will be
      the 4D tensor output of the
      last convolutional block.
  - `avg` means that global average pooling
      will be applied to the output of the
      last convolutional block, and thus
      the output of the model will be a 2D tensor.
  - `max` means that global max pooling will
      be applied.
* <b>`classes`</b>: optional number of classes to classify images
  into, only to be specified if `include_top` is True, and
  if no `weights` argument is specified.


#### Returns:

A Keras model instance.


## Compat aliases

* `tf.compat.v1.keras.applications.DenseNet169`
* `tf.compat.v1.keras.applications.densenet.DenseNet169`
* `tf.compat.v2.keras.applications.DenseNet169`
* `tf.compat.v2.keras.applications.densenet.DenseNet169`

