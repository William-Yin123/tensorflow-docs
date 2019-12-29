<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.applications.MobileNet" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.applications.MobileNet

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/applications/mobilenet.py">View source</a>



Instantiates the MobileNet architecture.

**Aliases**: `tf.keras.applications.mobilenet.MobileNet`

``` python
tf.keras.applications.MobileNet(
    input_shape=None,
    alpha=1.0,
    depth_multiplier=1,
    dropout=0.001,
    include_top=True,
    weights='imagenet',
    input_tensor=None,
    pooling=None,
    classes=1000,
    **kwargs
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`input_shape`</b>: optional shape tuple, only to be specified if `include_top`
  is False (otherwise the input shape has to be `(224, 224, 3)` (with
  `channels_last` data format) or (3, 224, 224) (with `channels_first`
  data format). It should have exactly 3 inputs channels, and width and
  height should be no smaller than 32. E.g. `(200, 200, 3)` would be one
  valid value.
* <b>`alpha`</b>: controls the width of the network. This is known as the width
  multiplier in the MobileNet paper. - If `alpha` < 1.0, proportionally
  decreases the number of filters in each layer. - If `alpha` > 1.0,
  proportionally increases the number of filters in each layer. - If
  `alpha` = 1, default number of filters from the paper are used at each
  layer.
* <b>`depth_multiplier`</b>: depth multiplier for depthwise convolution. This is
  called the resolution multiplier in the MobileNet paper.
* <b>`dropout`</b>: dropout rate
* <b>`include_top`</b>: whether to include the fully-connected layer at the top of
  the network.
* <b>`weights`</b>: one of `None` (random initialization), 'imagenet' (pre-training
  on ImageNet), or the path to the weights file to be loaded.
* <b>`input_tensor`</b>: optional Keras tensor (i.e. output of <a href="../../../tf/keras/Input.md"><code>layers.Input()</code></a>) to
  use as image input for the model.
* <b>`pooling`</b>: Optional pooling mode for feature extraction when `include_top`
  is `False`. - `None` means that the output of the model will be the 4D
  tensor output of the last convolutional block. - `avg` means that
  global average pooling will be applied to the output of the last
  convolutional block, and thus the output of the model will be a 2D
  tensor. - `max` means that global max pooling will be applied.
* <b>`classes`</b>: optional number of classes to classify images into, only to be
  specified if `include_top` is True, and if no `weights` argument is
  specified.
* <b>`**kwargs`</b>: For backwards compatibility only.


#### Returns:

A Keras model instance.



#### Raises:


* <b>`ValueError`</b>: in case of invalid argument for `weights`,
  or invalid input shape.

## Compat aliases

* `tf.compat.v1.keras.applications.MobileNet`
* `tf.compat.v1.keras.applications.mobilenet.MobileNet`
* `tf.compat.v2.keras.applications.MobileNet`
* `tf.compat.v2.keras.applications.mobilenet.MobileNet`

