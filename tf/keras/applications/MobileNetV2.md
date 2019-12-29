<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.applications.MobileNetV2" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.applications.MobileNetV2

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/applications/mobilenet_v2.py">View source</a>



Instantiates the MobileNetV2 architecture.

**Aliases**: `tf.keras.applications.mobilenet_v2.MobileNetV2`

``` python
tf.keras.applications.MobileNetV2(
    input_shape=None,
    alpha=1.0,
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


* <b>`input_shape`</b>: optional shape tuple, to be specified if you would
  like to use a model with an input img resolution that is not
  (224, 224, 3).
  It should have exactly 3 inputs channels (224, 224, 3).
  You can also omit this option if you would like
  to infer input_shape from an input_tensor.
  If you choose to include both input_tensor and input_shape then
  input_shape will be used if they match, if the shapes
  do not match then we will throw an error.
  E.g. `(160, 160, 3)` would be one valid value.
* <b>`alpha`</b>: controls the width of the network. This is known as the
width multiplier in the MobileNetV2 paper, but the name is kept for
consistency with MobileNetV1 in Keras.
  - If `alpha` < 1.0, proportionally decreases the number
      of filters in each layer.
  - If `alpha` > 1.0, proportionally increases the number
      of filters in each layer.
  - If `alpha` = 1, default number of filters from the paper
       are used at each layer.
* <b>`include_top`</b>: whether to include the fully-connected
  layer at the top of the network.
* <b>`weights`</b>: one of `None` (random initialization),
    'imagenet' (pre-training on ImageNet),
    or the path to the weights file to be loaded.
* <b>`input_tensor`</b>: optional Keras tensor (i.e. output of
  <a href="../../../tf/keras/Input.md"><code>layers.Input()</code></a>)
  to use as image input for the model.
* <b>`pooling`</b>: Optional pooling mode for feature extraction
  when `include_top` is `False`.
  - `None` means that the output of the model
      will be the 4D tensor output of the
      last convolutional block.
  - `avg` means that global average pooling
      will be applied to the output of the
      last convolutional block, and thus
      the output of the model will be a
      2D tensor.
  - `max` means that global max pooling will
      be applied.
* <b>`classes`</b>: optional number of classes to classify images
  into, only to be specified if `include_top` is True, and
  if no `weights` argument is specified.
* <b>`**kwargs`</b>: For backwards compatibility only.


#### Returns:

A Keras model instance.



#### Raises:


* <b>`ValueError`</b>: in case of invalid argument for `weights`,
  or invalid input shape or invalid alpha, rows when
  weights='imagenet'

## Compat aliases

* `tf.compat.v1.keras.applications.MobileNetV2`
* `tf.compat.v1.keras.applications.mobilenet_v2.MobileNetV2`
* `tf.compat.v2.keras.applications.MobileNetV2`
* `tf.compat.v2.keras.applications.mobilenet_v2.MobileNetV2`

